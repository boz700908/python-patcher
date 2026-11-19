## 本构建与原版的区别（中文网络适配）

- **多连接下载**：`-x 1 -s 8 -j 1` → `-x 16 -s 16 -j 4 -k 1M`。
  原版每服务器只开 1 条连接，GitHub 对单连接限速约 100 KB/s；改后实测可达 20+ MB/s。
- **镜像前缀**：自动探测可用的下载加速前缀并追加到所有外网地址；
  全部不可用时自动退回直连。可用 `mirror.txt`（每行一个前缀）或环境变量
  `SEVENTH_MOD_MIRROR` 覆盖。
- **Metalink 展开**：`.meta4` 会先展开成直链再下载，保证镜像前缀对内部地址同样生效。
- 未改动任何元数据（`installData.json` 等），安装流程与校验行为保持不变。

---

# Installation Instructions

- **Please download the installer to your computer, then run it - don't run directly from your browser**
- Please read the [Higurashi](https://07th-mod.com/wiki/Higurashi/Higurashi-Getting-started/) or [Umineko](https://07th-mod.com/wiki/Umineko/Umineko-Getting-started/) wiki sections for more information.

## Troubleshooting and Known Issues

- If you are having installer trouble, or the game does not run properly, follow the [**Support Checklist**](https://07th-mod.com/wiki/support-checklist/) to solve your problem
- **MacOS users may need to refresh the webpage (web GUI) if it does not load or seems to hang**.

## Windows Installer Variants Explanation

1. `07th-Mod.Installer.Windows.exe` (Requires Administrator)
    - Default Installer - **Try this first**.
2. `07th-Mod.Installer.Windows.SafeMode.exe` (Requires Administrator)
    - Use this if the installer does not start up. It uses a text-based interface for the launcher.
3. `07th-Mod.Installer.Windows.NoLauncher.zip` (No Administrator Required)
     - Use this if you cannot launch the above two .exes due to Antivirus, lack of Admin Priviledge, or crashes
     - You might need to install the [Visual C++ Redistributable (x86)](https://aka.ms/vs/16/release/vc_redist.x86.exe) ([linked from this page](https://support.microsoft.com/en-au/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0)), but most people will already have it.
     - Extract the `.zip` file to your desktop or downloads folder (NOT program files or the game root, as this may cause permissions issues)
     - Double click on the `install.bat` file.
        - A terminal will open, followed by a special page in your web browser (you use this webpage to install the mod).
        - If the `install.bat` does not work, close the terminal, then double click the `install_safe_mode.bat` for the text-only installer

## Important Changes

- put your changes here
