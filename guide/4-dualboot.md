<img align="right" src="../media/raphaelbutnotass.png" width="350" alt="运行在 Redmi K20 Pro 上的 Windows 11">

# 在 Xiaomi Mi 9T Pro / Redmi K20 Pro 上运行 Windows

## 实现 Android 和 Windows 无缝双系统启动

### 需要准备的文件
- [UEFI 镜像](https://github.com/new-WoA-Raphael/woa-raphael/releases/tag/UEFI)

- [WOA 助手](https://github.com/n00b69/woa-helper/releases/tag/APK)

## 设置双系统启动软件
> 这个指南默认认为你已经取得了 root 权限，如果你还没有 root，请先遵循[这个指南](root.md)。

### 设置 - Android 端
- 下载并安装 **WOA 助手**，然后打开它并授予其 root 权限。
- 下载 **UEFI 镜像**并将其放在你的内部存储中一个名为 `UEFI` 的文件夹。
- 打开 WOA 助手并点击**WOA 工具箱**，然后在弹出的页面中点击**将“切换到安卓”工具添加到 Windows**。
> [!Important]
> 如果 `/sdcard/Windows` 为空，则你的 rom 可能不支持挂载分区，你需要在 app 内制作一份 boot.img 的备份并在进入 Windows 后手动复制进去 (例如将其上传到某处后进入 Windows 并下载)。对于“切换到安卓”工具的文件做法也一样，文件将会生成在你的内部存储里。
>
> 如果文件夹为只读则也需这么做。
- 点击**快速启动到 WINDOWS** 按钮。

### 设置 - Windows 端
> [!Tip]
> 如果这是你第一次启动 Windows 且你想跳过登录微软账户的部分，请在要求连接 WiFi 时点击**我没有互联网**，然后点击**继续使用有限的体验**按钮。
>
> 如果并没有这几个按钮，点击屏幕顶端的**SIM 卡**按钮 (上面写着**已连接**的那个)，然后点击**断开连接**。
- 如果桌面上并没有切换到 Android 的快捷方式，导航到 `C:\sta` 并对 **sta.exe** 创建快捷方式并放到桌面上。

#### 启动到 Android
- 打开桌面上的新快捷方式 (你也可以将其固定到开始菜单或任务栏中以图方便)

#### 启动到 Windows
- 在 app 内点击 **快速启动到 WINDOWS**，或使用在快速设置面板内添加的按钮

> [!Important]
> 如果你更新或更换了你的 Android ROM，请确保创建一个新的 **boot.img** 的备份 (重启手机后！) 然后将其放置在 Windows 的 **C:\ 根目录**并覆盖旧文件。
>
> 你可以使用 WOA 助手中的**备份 BOOT 分区**功能来备份 boot.img 文件。

## 完成！









