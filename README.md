# Google Drive 视频批量下载器

一个 Windows 桌面工具：粘贴一个或多个你有权访问的 Google Drive 文件链接，即可批量下载，并支持断点续传、文件名处理与进度显示。

## 使用前提

请只下载你拥有或已获授权下载的内容，并遵守 Google Drive 的服务条款及适用法律。

## 运行源码

1. 安装 Python 3.12 或更高版本。
2. 在本项目目录执行：

   ```powershell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   pip install -r requirements.txt
   python .\google_drive_downloader.py
   ```

## 打包 Windows 程序

```powershell
pyinstaller --onefile --windowed --name "GoogleDrive视频下载器" google_drive_downloader.py
```

生成的程序位于 `dist` 目录。
