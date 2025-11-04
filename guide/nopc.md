<img align="right" src="../media/raphaelbutnotass.png" width="350" alt="运行在 Redmi K20 Pro 上的 Windows 11">

# 在 Xiaomi Mi 9T Pro / Redmi K20 Pro 上运行 Windows

## 不使用电脑安装 Windows

### 需要的工具
- 一个已经获取了 root 权限的 Xiaomi Mi 9T Pro / Redmi K20 Pro

- [修改版 TWRP](https://github.com/new-WoA-Raphael/woa-raphael/releases/download/Files/modded-twrp-raphael.img)

- [Raphael WinInstaller](https://github.com/new-WoA-Raphael/woa-raphael/releases/download/Files/RaphaelWinInstaller.zip)

- [WoA 镜像](https://arkt-7.github.io/woawin/)

- [WOA 助手](https://github.com/n00b69/woa-helper/releases/tag/APK)

- 可选: 一个 U 盘

### 注意
> [!WARNING]  
> 所有的数据都将被清除！如果需要的话请立即备份。
> 
> **不要重启你的手机！**如果你认为你做错了某一步，请前往 [Telegram 聊天](t.me/woaraphael)来寻求帮助。

> [!Important]
> 此教程假定了你已经有一台解了 BL 锁并取得了 root 权限的手机，如果你没有，则你还是需要一台电脑来完成。

### 输入修改版 TWRP
> 如果你已经安装过一个自定义的 recovery，你可以用其安装修改版 TWRP
- 下载修改版 TWRP，将其重命名为 **TWRP.img**并存在**内部存储**的 `Download` 文件夹内。
- 下载 **Termux**，打开它并授予其 root 权限。
- 在 Termux 内运行以下命令刷入 TWRP:
```cmd
su -c dd if=/sdcard/Download/TWRP.img of=/dev/block/by-name/recovery
```
- 在 Termux 内运行以下命令来重启到 TWRP:
```cmd
su -c reboot recovery
```
> 如果你刷入并重启后卡在了 fastboot 页面，请使用另一台手机对其刷入正确的 recovery 镜像，进入系统后备份当前的 boot 镜像并存放到另一台手机或 U 盘上，然后使用以下命令刷入修改版 TWRP
```cmd
su -c dd if=/sdcard/Download/TWRP.img of=/dev/block/by-name/boot
```
```cmd
su -c reboot
```

### 查看 data 解密是否正常
- TWRP 启动后，如果要求输入锁屏密码，则输入进去。
- 打开 TWRP 内的文件管理器，然后导航到你的内部存储。
> 如果你的文件都不见了且你的内部存储显示为 **(0MB)**，则会有一些额外步骤需要执行，具体将会稍后解释。

#### 打开 TWRP 终端
- 点击屏幕右下角的**高级**按钮，然后点击**终端**。

### 运行分区脚本
> 将 **$** 替换为你想要 Windows 可使用的容量大小 (不需要在结尾加上 GB，输入数值就行)
> 
> 如果它要求你再运行一次，照做即可。
```cmd
partition $
``` 

### 检查安卓是否还能正常运行
- 重启你的手机并查看安卓是否还能正常工作

### 准备需要的文件
- 将 Windows 镜像下载并保存到**内部存储**的 `Download` 文件夹内。
> [!Important]
> 由于性能原因，推荐使用 Windows 11 24H2 及以上 (版本号为 261XX 的，例如 26100.2454)

> 如果 TWRP 无法读/写你的内部存储，则在 **U 盘**上创建一个叫做 `WOA` 的文件夹并将 **.esd** 文件放在那里
>
> 或者，在网上再找一个可以解密你的 data 分区的 TWRP 镜像并使用
- 下载 **WinInstaller.zip** 并也将其放置在 `Download` 文件夹内。
- 下载并安装 [WOA 助手](https://github.com/new-WoA-Raphael/woa-helper/releases/tag/APK)，打开它并授予其 root 权限。先别碰软件里的任何东西。

#### 进入 TWRP
- 点击你的 root 管理器的右上角的`重启到 Recovery` 按钮。
- 进入 TWRP 后，按需输入锁屏密码。

### 刷入 WinInstaller
- 在 TWRP 里，点击**安装**然后找到 **WinInstaller.zip** 并刷入。
- 当你可以重启后，点击重启。
> [!Note]
> 等待所有过程完成后你的设备会进入 Windows。一般需要大概 15-20 分钟。

> [!Tip]
> 如果你想要跳过微软账号登录，在连接 WiFi 的页面点击**我没有互联网连接**，然后点击**继续使用有限的体验**按钮。

#### 进入 Android
- 运行桌面上的 **Android** 快捷方式 (你也可以把它固定到开始菜单/任务栏来更方便的访问)。

#### 进入 Windows
> 如果提示 "未找到 UEFI"，则下载 [UEFI 镜像](https://github.com/new-WoA-Raphael/woa-raphael/releases/tag/UEFI)并将其放置到内部存储中的 `UEFI` 文件夹内。
- 点击 WOA 助手中的**快速启动到 WINDOWS** 按钮或使用在快速设置面板里新添加的按钮。

## 完成！

























