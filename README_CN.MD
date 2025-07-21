# Linux DS SolidWorks 安装器 (Linux DS Solidworks Installer)

## 致谢
感谢项目 [SOLIDWORKS-for-Linux](https://github.com/cryinkfly/SOLIDWORKS-for-Linux) 本项目参考了该项目进行制作，并且改进了安装步骤，提高安装的成功率和运行成功率。

## 兼容性
该脚本已在 Arch Linux 上测试过，预计可以兼容其他发行版。

推荐安装 SolidWorks 2023/2025 版本：
- 2023 版本可在 GE-Proton 8-25 上运行（安装需要 Proton 9/Wine 9 以上版本，8 以下版本会卡在安装进度）。
- 2025 版本无法在此版本上运行，但可以在 GE-Proton 10-10 上正常运行与安装。

推荐使用 Lutris 或 Proton-Qt 来安装 Proton 环境，比较方便。

请自行从互联网上获取 SolidWorks 安装包，我们不提供下载。

## 已知问题
- UI 操作存在问题，无法正常点击左侧工具栏的按钮，需要使用键盘回车键来点击。
- SolidWorks 的其他组件可能无法正常运行，只有主程序能正常（带 BUG）运行。

## 软件包安装

### Arch Linux
```bash
sudo pacman -Sy winetricks wine python3 python-pip
pip3 install -r requirements.txt  # 安装环境
```
或者创建一个虚拟环境：
```bash
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
```

### Ubuntu/Debian
待补充

## 安装步骤
1. 首先从任何渠道获取正规或特殊的 SolidWorks 安装镜像（推荐使用 SolidWorks 2023/2025 版本）。
2. 首先确保你已安装 Proton 9.0 以上版本，可以使用 Lutris 或 ProtonUp-Qt 来安装 Proton。还需要安装 Winetricks。
3. 修改 environment.sh 文件，根据你的 Wine 安装包和 Proton 设置环境变量以及 SolidWorks 镜像名称。
4. 根据你的版本，使用 install.sh 或 install_ds.sh 来进行安装（带补丁的版本使用 install_ds.sh，原版使用 install.sh。
5. 手动安装完成 SolidWorks 后，进程会自动结束。选择你需要安装的额外组件，包括创建快捷方式。
6. 安装成功后，你可以通过 start.sh 或桌面的 SolidWorks 图标来启动 SolidWorks。