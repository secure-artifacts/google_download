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

## 如何发布新版本

本项目使用 GitHub Actions 自动构建和发布。每次发布新版本，只需推送一个以 `v` 开头的 Git 标签。

1. 确保代码已提交并推送：

   ```powershell
   git status
   git add .
   git commit -m "说明本次改动"
   git push origin main
   ```

2. 创建并推送版本标签，例如 `v1.0.1`：

   ```powershell
   git tag -a v1.0.1 -m "Release version 1.0.1"
   git push origin v1.0.1
   ```

GitHub Actions 会自动构建 Windows 程序、生成来源证明，并创建对应的 Release。请不要在 GitHub 网页中手动上传或替换 Release 文件，否则安全审核会无法验证构建来源。

如果构建失败，请在仓库的 Actions 页面查看日志，修复后删除失败标签并重新创建：

```powershell
git tag -d v1.0.1
git push origin :refs/tags/v1.0.1
git tag -a v1.0.1 -m "Release version 1.0.1"
git push origin v1.0.1
```
