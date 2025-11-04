<img align="right" src="../media/raphaelbutnotass.png" width="350" alt="运行在 Redmi K20 Pro 上的 Windows 11">

# 在 Xiaomi Mi 9T Pro / Redmi K20 Pro 上运行 Windows

## 额外材料
> 在下方你能找到一个包含 WoA 中的调整和额外材料的列表


### 支持的软件/游戏列表
> 这些绝非详尽无遗的清单，不过它们确实列出了社区已测试过的应用程序/游戏。

- [Renegade 谷歌表格](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

- [ARM 仓库 (原生 ARM 软件)](https://armrepo.ver.lt/)

- [新闻和支持的软件列表](https://windowsonarm.org/)

#### 完成！


### 切换 USB 主机模式
> [!Warning]
> 如果你正在使用带有独立供电的 USB 拓展坞，请关闭 USB 主机模式，因为这会对您的设备造成不可逆转的损坏。如果你没有在使用带有独立供电的 USB 拓展坞，启用 USB 主机模式否则你将无法使用任何 USB 设备。

- 运行 [USB 主机模式控制](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) 来启用/禁用 USB 主机模式，然后确认你真的想禁用/启用 USB 主机模式。
- 如果 USB 主机模式已经启用了但 USB 设备无法正常工作，将其关闭后再打开即可。

#### 完成！


### 设置自动刷入安卓的 boot.img
> [!NOTE]
> 设置在启动 Windows 后自动刷入安卓的 boot.img 或当电量不足 (<15%) 的时候自动刷入来防止在 UEFI 刷入的情况下电量耗尽。 

- 下载 **boot.img 自动刷入工具** [here](https://github.com/Misha803/My-Scripts/releases/tag/boot.img-Auto-Flasher).
- 运行并点击 **INSTALL** 按钮，选择你想要何时自动刷入安卓的 boot 镜像 (Windows 启动/低电量时) 并等待安装完成。
- 要卸载自动刷入工具，再次打开 **boot.img 自动刷入工具** 并点击 **UNINSTALL**。

#### 完成！


### 安装 Microsoft Office
- 前往 [Gravesoft 的 Office 安装程序页面](https://gravesoft.dev/office_c2r_links).
- 下载符合你的需求的安装程序。确保选择的是 `Online x64`。
- 打开 `setup.exe` 并按照其提示操作。

#### 完成！


### 激活 Windows / Office
- 使用 Massgravel 制作的[工具](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### 完成！


### 让键盘浮起
> [!WARNING]  
> 确保在运行 Windows 的设备上执行这些步骤，而不是你自己的电脑！

- 以管理员身份打开命令提示符并运行 ```reg delete HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Scaling /v MonitorSize```
- 输入 `y` 后回车。
- 重启你的设备。

##### 完成！




























