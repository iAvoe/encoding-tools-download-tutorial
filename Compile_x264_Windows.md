# Windows 编译 x264 的方法

本教程难度较高，阅读量和反复检查的内容量较大，适合有较多编程经验者实操。

1. 下载并安装 MSYS2：[www.msys2.org](https://www.msys2.org)
  - 选择安装文件夹步骤中，尽管可以考虑安装在非 `C:\msys64` 路径，但环境相关的程序一般都建议安装在系统盘，使运行环境对软件来说更像 Linux
  - 关闭安装后弹出的 UCRT64 命令行窗口
2. 在 MSYS2 安装文件夹（或开始菜单 MSYS2）下打开 `mingw64.exe` 命令行窗口，如 `C:\msys64\mingw64.exe`
  - 若不确定，可以用 `echo $MSYSTEM` 确认当前 CLI 窗口是 MINGW64
3. 运行软件包安装程序，从而配置编译 x264 所需的依赖（包括 FFmpegSource、L-SMASH 和 ffmpeg）
  - 安装 `mingw-w64-x86_64-toolchain` 时会弹出特定版本选项，按 Enter（全部安装）即可
  - 包括冲突提醒等选项按 Y 确认即可

......

打开 C:\msys64\mingw64.exe 并下载编译与依赖组件
```bash
pacman -S --needed \
  autotools \
  mingw-w64-x86_64-gcc \
  mingw-w64-x86_64-gdb \
  mingw-w64-x86_64-nasm \
  mingw-w64-x86_64-make \
  mingw-w64-x86_64-yasm \
  mingw-w64-x86_64-pkg-config \
  mingw-w64-x86_64-toolchain \
  git \
  base-devel \
  mingw-w64-x86_64-l-smash
```
4. 下载 ffmpeg，x264 源码（ffms2 编译暂时无法实现）
```bash
git clone https://github.com/FFmpeg/FFmpeg.git ffmpeg-static
git clone https://code.videolan.org/videolan/x264.git
# git clone https://github.com/FFMS/ffms2.git ffms2-static
```
5. 移动到 ffmpeg 目录，配置 ffmpeg 编译参数
  - 静态编译，注意该配置开启了非免费功能，不适合作为一般 ffmpeg 使用
```bash
cd ffmpeg-static

# 重复运行添加：make distclean

./configure \
  --prefix=/mingw64 \
  --enable-static \
  --disable-shared \
  --enable-gpl \
  --enable-version3 \
  --disable-programs \
  --enable-small \
  --disable-devices \
  --disable-filters \
  --disable-encoders \
  --disable-muxers \
  --disable-debug \
  --disable-sdl2 \
  --disable-network \
  --disable-protocols \
  --disable-doc \
  --enable-protocol=file,pipe \
  --enable-lzma \
  --enable-bzlib \
  --enable-zlib \
  --pkg-config-flags="--static" \
  --extra-cflags="-static -Wno-int-conversion" \
  --extra-cxxflags="-static -fpermissive" \
  --extra-ldflags="-static"
```
7. 编译与安装 ffmpeg 静态链接库（`-j` 启用多线程编译，但可能会遇到错误）
```bash
make -j && make install
```
8. ~~进入 FFMS2 源码根目录~~
```bash
cd ../ffms2-static
```
9. ~~FFMS2 更新子模块（只运行一次）~~
```bash
git submodule update --init --recursive
```
10. ~~修改 FFMS2 默认编译行为——静态链接库（只运行一次）~~
```bash
# 直接修改模板文件，修改 ffms2 不默认作为静态链接库之类的行为（和 Media_AutoBuild_Suite 一样）
sed -i 's/Cflags.*/& -DFFMS_STATIC/' ffms2.pc.in
# 如果不确定，可以用 cat ffms2.pc.in 检查：
# @configure_input@
# prefix=@prefix@
# exec_prefix=@exec_prefix@
# libdir=@libdir@
# includedir=@includedir@
# 
# Name: ffms2
# Description: The Fabulous FM Library 2
# Requires.private: libavformat libavcodec libswscale libavutil libswresample
# Version: @FFMS_VERSION@
# Libs.private: @ZLIB_LDFLAGS@ -lz
# Libs: -L${libdir} -lffms2
# Cflags: -I${includedir} -DFFMS_STATIC # 命令已添加
# Cflags.private: -DFFMS_STATIC -DFFMS_STATIC # 命令已添加
```
11. ~~配置 FFMS2 编译参数~~
```bash
# 重复运行添加：make distclean

# 运行 FFMS2 配置生成脚本（输出到 C:\msys64\mingw64\lib\pkgconfig\ffms2.pc）
./autogen.sh

./configure \
  --prefix=/mingw64 \
  --enable-static \
  --disable-shared \
  --disable-debug
```
12. ~~编译与安装 FFMS2 静态链接库~~
```bash
make -j && make install
```
13. 进入 x264 源码根目录
```bash
cd ../x264
```
14. 配置 x264 编译参数
```bash
# 重复运行添加：make distclean

./configure \
  --prefix=/mingw64 \
  --enable-static \
  --disable-opencl \
  --extra-ldflags="-static" \
  --extra-cflags="-march=native -Ofast -flto=auto -fext-dce"

# --extra-cflags="-march=native -O3 -flto=auto"
# --extra-cflags="-march=native -Ofast -flto=auto -fext-dce"

# 编译为 DLL（如替换 OBS 的 libx264.dll）：--enable-shared

# 故障——检测不到 ffms：ffms:           no
```
15. 编译与安装 x264 单文件
```bash
make -j
```

完成后，`x264.exe` 或 `x264.dll` 被输出到 `C:\msys64\home\<用户名>\x264\` 目录中

---

## 编译优化选项

编码器程序的编写本就重视执行效率，因此无需过于期待编译器优化的提升（也有例外）。尽管如此，视频编码，尤其是注重体积和画质的压制很耗时，因此用编译速度来换取压制速度的策略永远是划算的。所谓的编译器优化大致上代表以下处理：

| 术语                               | 功能             |
| ---------------------------------- | ---------------- |
| Dead Code Elimination (DCE)        | 精简赋值和计算   |
| Constant Folding                   | 函数直接返回结果 |
| Constant Propagation               | 变量转常量       |
| SSA + Copy Propagation             | 初始化直接赋值   |
| Global DCE                         | 删除无用全局变量 |
| Interprocedural Optimization (IPO) | 跨函数分析       |

分布到两种优化策略中：
- **链接时优化（Link-time Optimization）**：跨编译单元（跨 `.c`/`.cpp` 文件）地优化
- **程序整体优化（Whole Program Optimization）**：随编译过程分析并优化

### GCC 编译器优化选项

以上步骤中使用了 GCC 编译器，并开启了多个优化选项，以下是大致的解释：

- `-O`/`--optimize`：开启 GCC 优化，说明：[gcc.gnu.org](https://gcc.gnu.org/onlinedocs/gcc/Optimize-Options.html)
  - `-O3`：开启所有性能优化选项（多个选项）
  - `-Ofast`：开启所有性能优化选项，并且开启标准合规性限制选项（多个选项）
- `-flto`：开启链接时优化，`auto` 值指定启用多线程模式（默认仅单线程，并警告仅使用单线程 serial 模式）
- `-fwhole-program`：开启程序整体优化（失败：开启后报错 Endian test failed）
  - 限制：只能在编译程序是独立可执行文件（不是共享库），且不引用/调用外部库或程序时实现
- `-fext-dce`：开启数值位宽压缩，避免小的数值占用过多的 bit（通常无效）
- `-march`：根据 CPU 架构进行优化，可以指定“znver4 -mavx2 -mfma -mbmi2 -mpopcnt ...”等架构名参数值，native 代表当前电脑使用 CPU 的架构
  - GCC 和 CLang 同时支持该选项

---

## 测试编译结果

在 x264 源代码版本、源视频、编码参数相同的情况下测试（条件不严谨）：

[Media_AutoBuild_Suite（MABS）](https://github.com/m-ab-s/media-autobuild_suite) x264 r3221 编译结果：
  - encoded 32788 frames, 85.97 fps, 2999.18 kb/s

*无优化版 x264 r3223（速度第二）：*
  - encoded 32788 frames, 86.29 fps, 2999.18 kb/s

**`--extra-cflags="-march=native -O3 -flto` 优化版 x264 r3223：（第一）**
  - encoded 32788 frames, 86.31 fps, 2999.12 kb/s

*`--extra-cflags="-march=native -Ofast -flto -fext-dce` 优化版 x264 r3223（压缩第二）：*
  - encoded 32788 frames, 85.86 fps, 2999.12 kb/s

编译优化的确对 x264 产生了一点改善，并且由于代码效率提高，压缩率也增加了一点。不过，由于测试不够严谨，速度的变化可能纯粹是误差，可以忽略不计。

---

### 附录：编译选项说明

```
$ ./configure --help
```
用法：./configure [选项]

帮助：
`-h`，`--help` 显示帮助

目录选项：
`--prefix=PREFIX`：指定主安装目录（与架构无关的文件配置，默认 `/usr/local`）
`--exec-prefix=EPREFIX`：指定与架构相关的文件位置（默认与 prefix 相同）
`--bindir=DIR`：可执行文件安装目录（默认 `EPREFIX/bin`）
`--libdir=DIR`：库文件安装目录（默认 `EPREFIX/lib`）
`--includedir=DIR`：在 DIR 目录下安装包含文件 [PREFIX/include]

额外编译/链接标志（自定义优化或调试）：
`--extra-asflags=EASFLAGS`：将 EASFLAGS 添加到 ASFLAGS
`--extra-cflags=ECFLAGS`：将 ECFLAGS 添加到 CFLAGS
`--extra-ldflags=ELDFLAGS`：将 ELDFLAGS 添加到 LDFLAGS
`--extra-rcflags=ERCFLAGS`：添加 ERCFLAGS 到 RCFLAGS 的转换

基本功能：
`--disable-cli`：禁用命令行界面
`--system-libx264`：使用系统 libx264 库而非内部库
`--enable-shared`：构建共享库
`--enable-static`：构建静态库

Bash 命令行自动补全：
`--disable-bashcompletion`：禁用 bash-completion 脚本的安装
`--enable-bashcompletions`：强制安装 bash-completion 脚本
`--bashcompletionsdir=DIR`：将 bash-completion 脚本安装到指定目录 [auto]

编码功能：
`--disable-opencl`：禁用 OpenCL 功能
`--disable-gpl`：禁用仅限 GPL 协议的功能
`--disable-thread`：禁用多线程编码
`--disable-win32thread`：禁用 Win32 线程（仅限 Windows）

格式支持：
`--disable-interlaced`：禁用隔行扫描格式支持（或编码功能）
`--bit-depth=BIT_DEPTH`：设置输出位深度（8、10、全部）[全部]
`--chroma-format=FORMAT`：设置输出色度格式（400、420、422、444、全部）[全部]

高级选项：
`--disable-asm`：禁用汇编优化
`--enable-lto`：启用链接时优化

调试相关：
`--enable-debug`：添加调试符 `-g`
`--enable-gprof`：添加性能分析 `-pg`
`--enable-strip`：移除调试符号 `-s`（减小文件大小）
`--enable-pic`：生成位置无关代码（用于共享库）

交叉编译（如 Linux 上编译 Windows 版本）：
`--host=HOST`：目标平台
`--cross-prefix=PREFIX`：使用 PREFIX 指定交叉编译工具前缀（如 `arm-linux-gnueabi-`）
`--sysroot=SYSROOT`：目标系统的根路径

外部库支持：
`--disable-avs`：禁用 AviSynth 脚本（.avs）格式支持
`--disable-swscale`：禁用 ffmpeg swscale 缩放与色彩空间转换滤镜组
`--disable-lavf`：禁用 libavformat 封装处理库
`--disable-ffms`：禁用 FFmpegSource 解码库（实现精确到帧的时间码定位/索引支持）
`--disable-gpac`：禁用 GPAC（MP4 库）支持
`--disable-lsmash`：禁用 lsmash 轻量级 MP4/MOV 封装处理库（支持可分段 MP4）

注：禁用全部封装支持后，x264 只能输出视频流单文件（裸流），与 x265、SVT-AV1 等“次时代编码器”的行为相同，这是视频处理工作流变化、版权与利益因素变化等多重因素的结果。