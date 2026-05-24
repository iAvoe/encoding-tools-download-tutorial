# x264 x265 AV1 影片壓製相關工具下載合集 

## 急用版 x264、x265、SVT-AV1 壓制教學

**首頁：**[nazorip.site](https://nazorip.site/archives/1476)、**鏡像備份：**[Google盤](https://drive.google.com/drive/folders/1kFCeNGA_wiiLt-DSeI3cyY8vxlffgQcy?usp=sharing)、[百度雲](https://pan.baidu.com/s/1sbz8WztGTz3lcLzirHW_2w)

## 免責聲明與許可聲明

本教學用於學習與研究目的，不構成任何形式的商業使用建議或授權。

1. 本教學所提及的軟體、腳本及命令行工具（包括但不限於 FFmpeg、x264/x265、SVT-AV1、QAAC、VapourSynth 等）均由其各自的開發者和組織獨立維護，並受其原始許可證條款約束
2. 若用於商業或分發用途，請遵守相關的開源許可（如 GPL、BSD、MIT 等）以及各國/地區的專利法規
3. 本文件作者不對因使用本文所述內容造成的任何損失承擔責任；讀者應自行評估並承擔相應的法律與風險
4. 某些影音編解碼器（如 H.264、H.265、AAC）在部分地區仍受專利保護。商用項目請諮詢相關專利池（如 MPEG LA、Via Licensing）或使用免專利方案（如 AV1、Opus）

---

## 基本工具

| 工具 | 簡介 |
|------|------|
| **[mpv 播放器](https://mpv.io/installation/)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/mpv.png" alt="MPV-Player" width="600"></div><br>現代影片播放器，支持深度配置、訂製，缺點是界面僅英語，中文支持要看第三方修改版。[安裝教學](https://nazorip.site/archives/1052/) |
| **[ffmpeg<br>濾鏡工具與編碼器](http://ffmpeg.org/download.html)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/ffmpeg.svg" alt="FFMpeg" width="400"></div><br>影片、音訊、圖像處理的工具集，提供封裝、解封裝、濾鏡、影音處理與命令行調用介面，常被作為影像處理的核心工具 |
| **[Voukoder<br>剪輯軟體導出插件](https://www.voukoder.org/)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/voukoder.png" alt="Voukoder" width="600"></div><br>Premiere/Vegas/AE 開源導出插件。 |
| **[OBS<br>開源直播與錄製工具](https://obsproject.com/zh-cn/download)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/obs.png" alt="OBS" width="600"><img src="img/tools-download/obs-1.webp" alt="OBS-1" width="600"></div><br>適合錄製原素材或採集壓製前後對比影片，支持命令行設定編碼器，現代窗口和音訊捕獲方法，但也需要花時間配置~~和趟雷~~。 |
| **[MediaInfo<br>元數據讀取工具](https://mediaarea.net/zh-CN/MediaInfo)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/mediainfo-1.png" alt="Mediainfo" width="600"></div><br>開源媒體資訊查看器；許多影片分析軟體功能就是通過內建它為組件實現的。 |
| **[ffprobe<br>視音訊讀取與分析工具](http://ffmpeg.org/download.html)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/ffprobe-excel.png" alt="ffprobe-with-excel" width="600"></div><br>CLI 媒體元數據提取工具，既可以讀取一般元數據，也可以深入影片幀讀取“內部資訊”；<br>需要結合數據可視化軟體，如 [Pyzo](https://pyzo.org)，Excel，[Power BI](https://www.microsoft.com/en-us/power-platform/products/power-bi) 實現最終的可視化 |
| **[DXVA Checker](https://bluesky-soft.com/en/DXVAChecker.html)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/dxva-checker-2.png" alt="DXVA-Checker" width="600"></div><br>檢測 PC 支持的硬體編解碼能力 |
| **[Process Lasso](https://bitsum.com/)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/process-lasso.png" alt="process-lasso" width="600"><img src="img/tools-download/process-lasso-1.png" alt="process-lasso-1" width="600"></div><br>自動最佳化進程優先度與電源計劃工具，保證高占用軟體卡死時系統正常響應 |

**注**：目前沒有直播平台明確支持恢復直播會話的能力。因此當大型遊戲卡死，系統不響應，只能斷電重啟時，唯一的選擇是創建新直播，然後向舊會​​話發送消息以通知觀眾跳轉（對主播和觀眾來說都很麻煩）。雖然 Pro Balance 調度不包治百病，但它在一定程度上保證了系統更容易響應用戶操作，也減少了直播中斷的一種可能。但對於非常不穩定的程序或沒有透過烤機檢測硬體穩定性的工況來說還是會卡死。

## 調用編碼器的 GUI 工具

| 工具 | 簡介 |
|------|------|
| **[ShanaEncoder](https://shana.pe.kr/shanaencoder_download)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/shana-encoder.png" alt="shana-encoder" width="500"><img src="img/tools-download/shana-encoder-1.png" alt="shana-encoder-1" width="500"><img src="img/tools-download/shana-encoder-2.png" alt="shana-encoder-2" width="500"></div><br>ffmpeg-CLI 搭配部分 GUI，上手較慢。使用了 ffmpeg 內嵌的 libx264、libx265、NVEnc。 |
| **[Simple x264 Launcher](https://bitbucket.org/muldersoft/simple-x264-launcher/downloads/)** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/simple-x264-launcher.png" alt="simple-x264-launcher" width="600"></div><br>內嵌 AviSynth，支持便攜版 VapourSynth，額外支持 x265 和 NVEnc 編碼器，適合批次壓制。 |
| **小丸工具箱<br>鏡像：[百度雲](https://pan.baidu.com/s/1VHonGHoZ0DmQBNZaRjML2A?pwd=crhu) 提取碼 `crhu`** | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/xiaowan-toolbox.png" alt="simple-x264-launcher" width="600"></div><br>操作簡單、適合入門的中文軟體，內嵌 MediaInfo、mp4box、Mkvtoolnix。 |

### 其它編碼器調用工具

#### PowerShell 批處理智慧壓制工具（bbenc）

一款容易上手的強力效率工具。主打自動根據影片規格，用戶需求，電腦硬體等條件，給出 ffmpeg、vspipe（API 自適應）、avs2yuv（AviSynth(+) 自適應）、avs2pipemod、SVFI 源，到 x264、x265、SVT-AV1 編碼器參數的訂製。附帶 VS/AVS 腳本自動生成功能，以及複雜封裝命令生成工具。

- **首頁**：[NazoRip](https://nazorip.site/archives/1101/)
    - *[GitHub 項目頁](https://github.com/iAvoe/Batch-batch-encoder/tree/main)*
    - *[提問與回饋](https://github.com/iAvoe/Batch-batch-encoder/issues)*

## 影片畫質跑分工具

> 所有命令行工具的下載與教學見：[AV1 影片壓製教學](https://iavoe.github.io/av1-web-tutorial/HTML/index.html#h2-17)

總的來說，PSNR、SSIM 不準確，不可信；測量影片畫質應該選擇 Spearman 單調相關係數（SROCC）和 Pearson 線性相關係數（PLCC）高，並且性能可觀的畫質跑分工具，如：
- 客觀：塊大小感知加權峰值信噪比——XPSNR
- 主觀 + 客觀：多方法融合——Video multi-method assessment fusion（VMAF）
- 客觀：多失真識別多解析度結構相似性——SSIMULACRA
- 主觀 + 客觀：XYB 空間歐幾里得距離心理視覺相似性——Butteraugli

| 工具 | 簡介 |
|------|------|
| **[FFMetrics](https://github.com/fifonik/FFMetrics)**            | <div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/tools-download/ffmetrics.png" alt="FFMetrics" width="600"><img src="img/tools-download/ffmetrics-1.png" alt="FFMetrics-1" width="600"></div><br>測量 PSNR、SSIM、VMAF 的開源 GUI 軟體，支持即時圖表顯示和多版本並行排名。<br>需手動添加 ffmpeg 到程序目錄（或添加 ffmpeg 到 `%PATH%`） |
| **XPSNR（ffmpeg 內建）**                                          | 計算“源與壓縮結果的差異”，注重暫停畫質的深度改進版 PSNR，需要源影片與壓縮結果的時間基對齊 |
| **VMAF（ffmpeg 內建）**                                           | 主觀畫質指標跑分，傾向於檢查視覺觀感體驗，而非簡單地差異（如高壓縮下保證大體觀感），需要源影片與壓縮結果的時間基對齊 |
| **[SSIMULACRA2 VS-HIP](https://github.com/Line-fr/Vship)**       | 使用英偉達和 AMD 顯示卡計算 SSIMULACRA2.1、Butteraugli 的準確影片畫質跑分命令行工具，準確度同樣受到顯示卡快但精度低的影響 |
| **[SSIMULACRA2_rs](https://github.com/rust-av/ssimulacra2_bin)** | 使用 CPU 多執行緒計算 SSIMULACRA2.1，比 VS-HIP 的更慢，且需要編譯、需要 Python-VapourSynth 環境，優點是精度更高（由於和畫質相關，因此得分也更高） |

> 儘管 FFMetrics 在導入文件時限制了格式範圍，但它直接調用了 ffmpeg，因此可以選擇“所有文件”來選中新編碼格式的影片串流

> VMAF 可在 [Netflix/vmaf](https://github.com/Netflix/vmaf) 獲取最新版模型與運行腳本，但 ffmpeg 內建版本更容易實現多影片批次檢測

> SSIMULACRA2_rs 支持手動指定多執行緒參數，從而顯著提高速度

### 時間基對齊工具

總的來說，由於部分影片畫質跑分需要統計幀間距離等數據，因此源與壓縮影片的時間基（Time base）需要對齊，否則跑分會嚴重失真（變差）。詳見 AV1 教學完整版、AV1 教學精簡版。

**GitHub：**[GitHub/GCDLCMCalcualtor](https://github.com/iAvoe/GCDLCMCalculator-VideoQualityMetrics)、**鏡像備份：**[Google盤](https://drive.google.com/drive/folders/1kFCeNGA_wiiLt-DSeI3cyY8vxlffgQcy?usp=sharing)、[百度雲](https://pan.baidu.com/s/1sbz8WztGTz3lcLzirHW_2w)

### SSIMULACRA2_rs 下載與編譯

> 來源：[GitHub/rust-av](https://github.com/rust-av/ssimulacra2_bin)

#### 1. 編譯環境

1. 下載並安裝 rustup：[rustup.rs](https://rustup.rs)
2. **完整安裝** [VapourSynth](https://github.com/vapoursynth/vapoursynth/releases)
  - **必須**安裝到 `C:\Program Files\VapourSynth`
  - **必須**選擇“Install for all users”
3. **完整安裝** [Python](https://www.python.org)
  - **必須**以管理員身份運行
  - **必須**在自訂安裝中選擇“Install for all users”
  - VapourSynth 的版本與 Python 版本強綁定，不能隨意安裝版本
4. 檢查 `C:\Program Files\VapourSynth\sdk\lib64` 路徑存在，若不存在則上述步驟執行有誤，需卸載 Python 和 VapourSynth，仔細閱讀並重試

#### 2. 下載與編譯

5. PowerShell 中運行 `cargo install ssimulacra2_rs`完成安裝，過程中不應該有任何報錯
6. 將 `C:\Users\使用者名稱\.cargo\bin\ssimulacra2_rs.exe` 拷貝到工作路徑
  - 此時可以卸載 rustup
7. 下載 LSMAS 解碼器：[GitHub/AkarinVS](https://github.com/AkarinVS/L-SMASH-Works/releases)
8. 隨意根據想要的快取文件路徑位置設定選擇版本：
  - 官方：<code>cachedir=""</code>，命令行窗口當前路徑，Windows 預設為 C 槽
  - cwd：<code>cachedir="."</code>，即運行時的命令行路徑，即打開 CMD/PowerShell/Bash 時的初始路徑
  - tmp：<code>cachedir=%TEMP%</code>，據操作系統設置指定快取盤，Windows 一般為 C 槽
8. 解壓並拷貝下載的 `LSMASHSource.dll`、`LSMASHSource.pyd` 到 VapourSynth 插件目錄下：
  - `C:\Program Files\VapourSynth\plugins`

> ssimulacra2_rs 在 PowerShell 中無法正常列印資訊，需要使用 CMD 運行

> LSMAS 快取文件代表“O__&lt;影片檔案名&gt;.lwi”索引文件，這些文件相當於快取，但運行完後需要手動刪除

---

## 音訊編碼器

為減少篇幅，此處之提供兩個高音質音訊編碼器選項。

### QAAC

注重高音質的 AAC 格式音訊編碼器，依賴蘋果 CoreAudio。安裝與使用見 **[QAAC 音訊壓製教學](https://www.nazorip.site/archives/44)** 或 **[GitHub 副本](https://github.com/iAvoe/QAAC-Tutorial-Standalone/blob/master/%E6%95%99%E7%A8%8B.md)**

<div style="display: flex; justify-content: center; align-items: center;"><img src="img/audio-codec-download/AAC_original_logo.svg" alt="aac-logo" width="200"></div>

> 圖片來源：[Wikipedia](https://en.wikipedia.org/wiki/File:AAC_original_logo.svg)

### OPUS

<div style="display: flex; justify-content: center; align-items: center;"><img src="img/audio-codec-download/opus-logo.svg" alt="opus-logo" width="300"></div>

> 圖片來源：[OPUS 官網](https://opus-codec.org/)

完全開放、免版稅、多用途的 OGG 格式音訊編碼器，一般直接通過 ffmpeg 調用。或者可以根據 [OPUS 官網](https://opus-codec.org) 的文件下載與調用 libopus。

---

## 影片濾鏡工具

建議直接學習 VCB-S 壓制組的教學系列：[vcb-s.nmm-hd.org](https://vcb-s.nmm-hd.org/)

| 工具 | 簡介 |
|------|------|
| **[VapourSynth](https://github.com/vapoursynth/vapoursynth/releases)** | 源影片有時帶有畫面問題，就靠它修復。安裝時應注意不同版本對 Python 環境有強綁定。**安裝：[vapoursynth.com](https://www.vapoursynth.com/doc/installation.html)** |
| **[AviSynth+](https://github.com/AviSynth/AviSynthPlus/releases)**     | 含多執行緒最佳化，添加高位深支持的老款影像處理工具 AviSynth。現已被更先進的 VapourSynth 取代，但還有些濾鏡仍是獨占。 |
| **[avs2yuv](https://github.com/DJATOM/avs2yuv/releases)**              | 相當於 VapourSynth 中的 VSPipe.exe，使導出 AviSynth 到管道（pipe）變得容易。 |
| **[avs2pipemod](https://github.com/chikuzen/avs2pipemod/releases)**    | 相當於 VapourSynth 中的 VSPipe.exe，使導出 AviSynth 到管道（pipe）變得容易。 |

---

## 影片編碼器

**lavf（LibavFormat）**：負責封裝/解封裝的動態連結庫。

**FFMS2（FFmpegSource2）**：負責解碼的動態連結庫，用於給 x264 內建的 AviSynth 提供解碼後的源。

### x264

<div style="display: flex; justify-content: center; align-items: center;"><img src="img/x264-x265-download/x264_fire_final.png" alt="x264-logo" width="500"></div>

> 來源：[Wikipedia](https://commons.wikimedia.org/wiki/File:X264.png)

| 來源 | 封裝支持 | 特性 |
|------|---------|------|
| **[Patman](https://www.mediafire.com/folder/arv5xmdqyiczc)** | ✅ FFMS2 解碼、Lavf 封裝              | 8-10bit |
| **[LigH](https://www.mediafire.com/?bxvu1vvld31k1)**         | ✅ FFMS2 解碼、Lavf 封裝              | 8-10bit |
| **[jspdr (tMod)](https://github.com/jpsdr/x264/releases/)**  | ✅ FFMS2 解碼、Lavf 封裝              | 8-10bit，MCF 執行緒管理 |
| **x264 7mod<br>[Google盤](https://drive.google.com/drive/folders/1kFCeNGA_wiiLt-DSeI3cyY8vxlffgQcy?usp=sharing)<br>[百度雲](https://pan.baidu.com/s/1sbz8WztGTz3lcLzirHW_2w)** | ✅ FFMS2 Lavf 解碼與封裝 | 8-10bit，hqdn3d 時域降噪 |
| **[Komisar (KMod)](http://komisar.gin.by/)**                 | ✅ FFMS2 解碼、Lavf 封裝               | 8, 10bit |

> [8-10-12bit] 表示一個可同時支持三種色深的可執行文件；

> [8][10][12]bit 表示三種不同可執行文件版本。  

### 自行編譯 x264

- [使用 media-autobuild_suite 自動編譯](https://github.com/m-ab-s/media-autobuild_suite)
  - 極其強大，文件也多的一站式多重工具一次性編譯腳本系統
- [Windows 手動編譯 x264（有微小性能與壓縮率提升）](.\Compile_x264_Windows.md)
  - 缺點是未實現 ffmpegSource 模組集成（其中一個影片源直接導入的解碼工具），不過幾乎沒有影響

---

### x265

<div style="display: flex; justify-content: center; align-items: center;"><img src="img/x264-x265-download/X265_(HEVC_encoder,_logo).svg" alt="x265-logo" width="400"></div>

> 來源：[Wikipedia](https://en.wikipedia.org/wiki/File:X265_%28HEVC_encoder%2C_logo%29.svg)

影片編碼器本體不支持額外的解碼與封裝/解封裝功能並非缺陷。影片編碼器本身不處理音訊串流，因此壓製影片後，音訊串流仍需封裝。此外，x265、AV1、VVC 等較新編碼的未封裝格式能夠提供幀率、解析度、色彩格式等全局元數據，因此未封裝狀態下也可在影片播放器中預覽。

| 來源 | 編碼器封裝音訊 | 色深支持 | 特性 |
|------|------------|---------|------|
| **[LigH](http://www.mediafire.com/?6lfp2jlygogwa)**                               | ⛔ `.hevc` 裸流 | 8-10-12bit      | 附 x86 32bit 版，含 libx265.dll |
| **[jpsdr](https://github.com/jpsdr/x265/releases)**                               | ⛔ `.hevc` 裸流 | 8-10-12bit      | GCC 12.2 + MSVC_llvm 1928，支持 aq-mode 5 |
| **[Rigaya](https://drive.google.com/drive/folders/0BzA4dIFteM2dWEpvWGZXV3ZhdTA)** | ⛔ `.hevc` 裸流 | 8-10-12bit      | GCC 9.3，附 32bit 版 |
| **[Patman](https://github.com/Patman86/x265-Mod-by-Patman/releases)**             | ⛔ `.hevc` 裸流 | 8-10-12bit      | GCC 11 + MSVC 1925 |
| **[ShortKatz](https://forum.doom9.org/showthread.php?p=1937773#post1937773)**     | ⛔ `.hevc` 裸流 | 8-10-12bit      | arm64~64e 的 Mac 與安卓平台使用 |
| **[DJATOM-aMod](https://github.com/DJATOM/x265-aMod/releases/)**                  | ⛔ `.hevc` 裸流 | 10bit, 10-12bit | LLVM 的針對 Intel 與 AMD 架構最佳化版 |
| **[MeteorRain-yuuki](https://down.7086.in/)**                                     | ✅ Lavf 封裝庫  | 8, 10, 12bit    | GCC 9.3 + ICC 1900 + MSVC 1916 |

> 未使用 y4m 或 lavf 時應手動指定 `-D` 參數

---

### SVT-AV1

<div style="display: flex; justify-content: center; align-items: center;"><img src="img/svt-av1-download/AV1_logo_2018.svg" alt="av1-logo" width="400"></div>

> 來源：[Wikipedia](https://commons.wikimedia.org/wiki/File:AV1_logo_2018.svg)

編碼器由兩個文件組成：`SvtAv1Enc.dll`、`SvtAv1EncApp.exe`
- Clang（LLVM）針對當前 PC CPU 架構編譯版本的性能最佳，其次是 GCC，再次為 MSVC（Visual Studio）；性能差異最高可達 10%~50%

| 來源 | 編碼器封裝音訊 | 色深支持 | 已編譯 | 特性 |
|------|------------|---------|--------|------|
| **[SVT-AV1](https://gitlab.com/AOMediaCodec/SVT-AV1)**                                                      | ⛔ `.ivf` 微封裝   | 8-10bit | ⛔ | 官方版 |
| **[Gitlab Pipelines](https://gitlab.com/AOMediaCodec/SVT-AV1/-/pipelines)**                                 | ⛔ `.ivf` 微封裝   | 8-10bit | ✅ | 官方 CI/CD 版，屬於一種 Beta 測試版，但無需編譯。找到最新通過的 Daily Run 計劃，選擇對應系統版本下載 |
| **[SVT-AV1-Essential by nekotrix](https://github.com/nekotrix/SVT-AV1-Essential/releases)**                 | ⛔ `.ivf` `.webm` | 8-10bit | ✅ | 改良默認參數預設，增加了新功能（參數），如自動計算瓦片大小，CRF 分區賦值（zones），高精度去塊濾鏡（dlf 2），固定執行緒占位等 |
| **[SVT-AV1-Essential by Patman86](https://github.com/Patman86/SVT-AV1-Mods-by-Patman/tree/Essential-PMod)** | ⛔ `.ivf` 微封裝   | 8-10bit | ✅ | 改良默認參數預設（以及調整預設 5-2），增加了新功能（參數），如自動計算瓦片大小，CRF 分區賦值（zones），超高精度去塊濾鏡（dlf 3），色度專用 FGS，固定執行緒占位等 |
| **[SVT-AV1-HDR by Patman86](https://github.com/Patman86/SVT-AV1-Mods-by-Patman/tree/HDR-PMod)**             | ⛔ `.ivf` 微封裝   | 8-10bit | ✅ | 改良默認參數預設，增加了 HDR 最佳化，如針對 PQ 最佳化的 Variance Boost 曲線，膠片顆粒 Tune，關鍵幀專用 TF 衰減偏移值，空間噪聲分布一致化等 |
| **[SVT-AV1-PSY](https://github.com/psy-ex/svt-av1-psy)**                                                    | ⛔ `.ivf` 微封裝   | 8-10bit | ⛔ | 增加了更高畫質選項的修改版，目前主要的最佳化已經合併到了 SVT-AV1 官方版，且已停止開發，版本落後於官方，與官方版一樣需要編譯 |

---

### 選項一——Windows 手動編譯 SVT-AV1

步驟相對簡單，適合計算機新手實操的方法。

> 官方指南：[Build Guide](https://gitlab.com/AOMediaCodec/SVT-AV1/-/blob/master/Docs/Build-Guide.md)

1. 安裝 **Visual Studio**（2017/2019/2022）並啟用 **C++ 桌面開發組件**  
2. 安裝 **CMake**：[CMake Releases](https://github.com/Kitware/CMake/releases#gh-md-img-large)<br><div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/svt-av1-download/cmake-sm.png" alt="CMake" width="400"></div>
3. 安裝 **NASM**：[NASM 官方下載](https://www.nasm.us/pub/nasm/releasebuilds/?C=M;O=D)<br><div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/svt-av1-download/nasm.svg" alt="NASM" width="200"></div>
    - 在打開的網路硬碟路徑中根據系統和指令集位寬找最新版程序 
        - 例如，Windows 64bit 選擇 最新版/win64/nasm-***-installer-x64.exe
    - 安裝時可以去勾選 Manual（說明書）和 VS8 Integration（Visual Studio 8 集成）
4. 下載 [SVT-AV1 原始碼](https://gitlab.com/AOMediaCodec/SVT-AV1/-/archive/master/SVT-AV1-master.zip) 並運行 `Build/windows/build.bat`  
5. 編譯輸出位於 `Bin\Debug`，確認可執行文件存在後測試：  
```bash
SvtAv1EncApp.exe -v
```
---

### 選項二——使用 Clang（LLVM）編譯 SVT-AV1（推薦）

步驟相對複雜（但比 x264 編譯簡單），但性能大幅提高，適合有一點編程經驗者的方法。

> 所有命令建議在 **CMD 或 (Git) Bash** 中執行，不要使用 PowerShell。

#### 1. 編譯環境

<div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/svt-av1-download/llvm.png" alt="LLVM" width="400"></div>

1. **LLVM（clang 支持）**：[LLVM Releases](https://github.com/llvm/llvm-project/releases/latest)
   - 在打開的網路硬碟路徑中根據系統和指令集位寬找最新版程序 
     - 例如，Windows 64bit 操作系統選 LLVM-***-win64.exe
   - 安裝時選擇 Add LLVM to the system PATH for all/current users
2. **Microsoft C++ Build Tools**：[Microsoft C++ Build Tools](https://visualstudio.microsoft.com/vs/visual-cpp-build-tools)
   - 如果已經安裝 Visual Studio，且直接下載了 C++ 桌面應用開發組件，則可以跳過這步
   - 下載並運行安裝程式，選擇 Desktop development with C++
   - 打開一個記事本，將實際安裝位置路徑拷貝進去
   - 安裝頁面中，可以僅選擇安裝 MSVC 和最新的 Windows 10/11 SDK
3. **CMake**、**NASM**：與上方教學步驟一致
4. Git（可選）：git-scm.com/download/win
5. 編譯前確認所有工具正確安裝（命令行能正確輸出）
```batch
:: 如果安裝時選擇其它路徑，則修改
"C:\Program Files\LLVM\bin\clang.exe" --version
:: clang version ***
:: Target: x86_64-pc-windows-msvc
:: Thread model: posix
:: InstalledDir: C:\Program Files\LLVM\bin

where clang-cl
:: C:\Program Files\LLVM\bin\clang-cl.exe

nasm --v
:: NASM version *** compiled on *** *** ***
cmake --version
:: cmake version ***
:: CMake suite maintained and supported by Kitware (kitware.com/cmake)
```

#### 2. 下載項目原始碼

##### a. 瀏覽器下載

將 GitLab/AOMediaCodec/SVT-AV1 項目 [打包下載](https://gitlab.com/AOMediaCodec/SVT-AV1/-/archive/master/SVT-AV1-master.zip) 並解壓

##### b. Git 下載

若照上面安裝了 Git，則打開 Git Bash，並使用下方命令下載：

1. 移動到下載路徑（不同的命令行工具路徑格式和要求不同）
  - `cd <下載路徑>`
  - 例：下載到 D 槽桌面：`cd /d/Desktop/`
2. 下載 SVT-AV1
  - `git clone https://gitlab.com/AOMediaCodec/SVT-AV1.git`
  - `cd svt-av1`

#### 3. 編譯項目

**完整命令行列表（僅供參考，無法一次執行）**
```batch
chcp 65001
call "C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\VC\Auxiliary\Build\vcvars64.bat"
set "CC=clang-cl"
set "CXX=clang-cl"

cmake --fresh -B svt_build -G Ninja ^
-DCMAKE_BUILD_TYPE=Release ^
-DBUILD_SHARED_LIBS=OFF ^
-DCMAKE_CXX_FLAGS_RELEASE="-flto /DNDEBUG /clang:-O2 -march=native"
```

1. 切換文本編碼到 UTF-8：
```batch
chcp 65001
```
2. 在先前下載的 VS Build Tools 路徑中運行 vcvars64.bat 環境配置腳本（根據實際安裝位置調整）：
```batch
call "C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\VC\Auxiliary\Build\vcvars64.bat"
```
> 若已經有了“C++ 桌面應用開發組件”的 64bit Visual Studio，則路徑可能是：

> `C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build\vcvars64.bat`

<div style="display: flex; justify-content: center; align-items: center; flex-direction: column;"><img src="img/svt-av1-download/vcvars64.png" alt="vcvars64" width="600"></div>

> 圖：x64 Native Tools Command Prompt for VS 20xx

3. 運行 vcvars64.bat 後會進入一個新的 CMD 界面，在此指定兩個變數以定義使用 Clang-CL 編譯器：
```batch
set "CC=clang-cl"
set "CXX=clang-cl"
```
4. 用 CMake 生成 Ninja 項目並配置編譯選項（根據壓制電腦的 CPU 架構進行調整）：
  - 如果當前目錄不在 SVT-AV1 或 SVT-AV1-PSY 目錄下，則使用 `cd` 移動過去
  - 如果 CPU 支持 AVX-512，且比 ZEN 2 架構新，則推薦 `-DENABLE_AVX512=ON`
```batch
:: 換行符取決於終端軟體，CMD 使用 `^`，Bash 使用 `\`
:: 如果要編譯 Debug 版而非發布版，則去掉 `-DCMAKE_BUILD_TYPE=Release` 整行
cmake --fresh -B svt_build -G Ninja ^
-DCMAKE_BUILD_TYPE=Release ^
-DBUILD_SHARED_LIBS=OFF ^
-DENABLE_AVX512=OFF ^
-DSVT_AV1_LTO=OFF ^
-DCMAKE_CXX_FLAGS_RELEASE="-flto /DNDEBUG /clang:-O2 -march=native" ^
-DCMAKE_C_FLAGS_RELEASE="-flto /DNDEBUG /clang:-O2 -march=native"
```
5. 最後使用 Ninja 編譯，不用 `-DCMAKE_BUILD_TYPE=Release` 則會輸出到 Bin\Debug）：：
```batch
ninja -C svt_build
:: *** warnings generated.
:: D[242/242] Linking C executable *:\***\SVT-AV1-master\Bin\Release\SvtAv1EncApp.exe
```

---

## 編碼器官方開源項目

基本上有以下用途：
- 下載並檢查、修改、編譯原始碼
- 檢查變更提交（Commit）的更新資訊
- 向開發者回饋編碼器問題（Issues）

| 影片編碼器項目                                                                             | 簡介                                               |
| ----------------------------------------------------------------------------------- | ------------------------------------------------ |
| **[x264 – VideoLAN](https://code.videolan.org/videolan/x264)**                      | H.264/AVC 編碼器，由 VideoLAN 團隊維護，廣泛用於 FFmpeg、OBS 等。 |
| **[x265 – MulticoreWare](https://bitbucket.org/multicoreware/x265_git/src/master)** | H.265/HEVC 編碼器的主要開源實現。                           |
| **[SVT-AV1 – AOMedia](https://gitlab.com/AOMediaCodec/SVT-AV1)**                    | Intel 維護的高性能 AV1 編碼器，屬於 AOMedia 官方 SVT 系列。       |
| **[libaom – AOMedia](https://aomedia.googlesource.com/aom/)**                       | AOMedia 官方 AV1 編碼器參考實現（品質優先）。                    |
| **[rav1e – Xiph / Mozilla](https://github.com/xiph/rav1e)**                         | 用 Rust 編寫的 AV1 編碼器，專注安全與速度。                      |
| **[vpx – WebM / Google](https://chromium.googlesource.com/webm/libvpx/)**           | Google 的 VP8/VP9 官方實現。                           |
| **[SVT-HEVC – Intel](https://github.com/OpenVisualCloud/SVT-HEVC)**                 | Intel 的高性能 HEVC 編碼器（面向伺服器/雲轉檔）。                  |
| **[SVT-VP9 – Intel](https://github.com/OpenVisualCloud/SVT-VP9)**                   | Intel 的 VP9 編碼器實現。                               |
| **[openh264 – Cisco](https://github.com/cisco/openh264)**                           | Cisco 開源的 H.264 編碼器，輕量級且廣泛用於即時通信。                |
| **[Theora – Xiph.Org](https://gitlab.xiph.org/xiph/theora)**                        | 基於 VP3 的開放影片編碼標準。                                |
| **[FFmpeg – FFmpeg.org](https://github.com/FFmpeg/FFmpeg)**                         | 雖非單獨編碼器，但整合了 x264、x265、libaom、SVT 等眾多編碼器。        |
| **[Daala – Xiph.Org](https://gitlab.xiph.org/xiph/daala)**                          | Xiph 的實驗性下一代影片編碼器（為 AV1 提供技術基礎）。                 |
| **[VVenC – Fraunhofer HHI](https://github.com/fraunhoferhhi/vvenc)**                | Fraunhofer HHI 的 VVC (H.266) 開源編碼器。              |
| **[VVC Test Model (VTM)](https://vcgit.hhi.fraunhofer.de/jvet/VVCSoftware_VTM)**    | JVET 官方 VVC/H.266 參考軟體實現。                        |


| 音訊編碼器項目                                                                  | 簡介                                                     |
| ------------------------------------------------------------------------ | ------------------------------------------------------ |
| **[QAAC – nu774](https://github.com/nu774/qaac)**                        | 基於 Apple CoreAudio 的 AAC 編碼器前端（Windows 上需 iTunes DLL）。 |
| **[Opus – Xiph / Mozilla / Skype](https://gitlab.xiph.org/xiph/opus)**   | IETF 標準化的低延遲音訊編碼器，適用於語音與音樂。                            |
| **[libopusenc – Xiph.Org](https://gitlab.xiph.org/xiph/libopusenc)**     | 封裝 Opus 編碼 API 的簡易庫，用於錄音或即時流。                          |
| **[FDK-AAC – Fraunhofer IIS](https://github.com/mstorsjo/fdk-aac)**      | Fraunhofer 官方開源 AAC 編碼器（高品質 LC/HE/HEv2 模式）。            |
| **[LAME – HydrogenAudio](https://lame.sourceforge.io/)**                 | 著名的開源 MP3 編碼器。                                         |
| **[FLAC – Xiph.Org](https://gitlab.xiph.org/xiph/flac)**                 | 無損音訊壓縮格式 FLAC 的官方實現。                                   |
| **[Vorbis – Xiph.Org](https://gitlab.xiph.org/xiph/vorbis)**             | Xiph.Org 的有損音訊編碼器，開源替代 MP3。                            |
| **[Musepack (MPC)](https://github.com/MusepackProject/musepack)**        | 專注高位元率透明音質的音訊編碼器。                                      |
| **[WavPack](https://github.com/dbry/WavPack)**                           | 無損/有損混合音訊編碼器。                                          |
| **[ALAC – Apple](https://github.com/macosforge/alac)**                   | Apple 無損音訊編解碼器（ALAC）的開源實現。                             |
| **[TTA – True Audio](http://true-audio.com/)**                           | 無損音訊編碼格式 TTA 的官方實現。                                    |
| **[Monkey’s Audio (APE)](https://github.com/monkeysaudio/Monkey-Audio)** | 高壓縮率的無損音訊編碼器。                                          |
| **[Shorten – SoftSound](https://github.com/robdobsn/shorten)**           | 早期無損音訊格式（FLAC 的前身之一）。                                  |

---

## 參考

SVT-AV1 CLang LLVM 編譯的原教學位於 [Discord/AV1 weeb edition/scripts-tools-and-guides](https://discord.com/channels/992019264959676448/1253334764920766505)，本教學進行了在地化（如修改 set 命令、添加 chcp 命令），以及額外說明（如 Visual Studio 已經安裝的 vcvars），額外引導（下載具體版本），以及額外的檢查（LLVM、NASM、CMAKE 是否正確安裝）等改進。
