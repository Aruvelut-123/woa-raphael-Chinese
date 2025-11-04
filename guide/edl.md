<img align="right" src="../media/raphaelbutnotass.png" width="350" alt="运行在 Redmi K20 Pro 上的 Windows 11">

# 在 Xiaomi Mi 9T Pro / Redmi K20 Pro 上运行 Windows

## 使用 EDL 模式恢复你的设备

### 需要准备的文件
- [官方线刷包](http://xmfirmwareupdater.com/miui/raphael/)

- [EDL 驱动](https://github.com/new-WoA-Raphael/woa-raphael/releases/download/Files/QUD.zip)

- [修改版 MiFlash](https://github.com/new-WoA-Raphael/woa-raphael/releases/download/Files/PatchedMiflashRaphael.zip)

### 启动到 EDL 模式
> [!Note]
> 如果你已经进入 EDL 模式，则请跳过这步并前往"开始刷机"部分
- 如果你已经解锁了 BL 锁且能够访问 fastboot 模式，则只需在 fastboot 模式下使用 ```fastboot oem edl``` 即可进入 EDL 模式。

> 如果你的 BL 锁已锁定，或安卓系统无法正常启动且无法以任何形式访问 fastboot 模式，则你需要拆开后盖并短接 EDL 测试点或使用 EDL 测试线
>
> (并非所有的 EDL 测试线都可以使用且你可能会在无法使用的线缆上浪费钱，但这可能还是比拆开你的设备要更好)。
- 寻找名字里带有 **V2** 的线，例如 **Hydra V2 深刷线** 或 **V2 9008 深刷线**。并确保其为 USB-C 接口的线缆。
- 将线缆插入你的设备，然后按住线缆上的按钮，大概长[这样](https://t.me/nabuwoa/204867)（可能无法访问，因为此链接为 **Telegram** 的链接）。
- 你现在就应该进入了 EDL 模式。

### 安装 EDL 驱动
> 如果你的设备在**设备管理器**内的名称为 **QUSB_BULK_CID** 或有一个 ⚠️ 带有感叹号/问号的黄色三角形，且被分类到其他类里 (例如**其他设备**)，则你需要先安装 EDL 驱动。
- 要安装 EDL 驱动，解压 **QUD.zip** 到某个地方，然后在**设备管理器**上右键点击 **QUSB_BULK_CID**，然后点击**更新驱动程序**并点击**浏览我的电脑并查找驱动程序**，最后找到并选择解压出来的 **QUD** 文件夹。

### 开始刷机
- 打开 **XiaoMiFlash.exe** 并给予管理员权限。
- 下载你的设备的原厂线刷包 (后缀名应该为 .tgz) 并打开它。里面应该有一个后缀为 .tar 的文件。将其解压到任意一个文件夹内。
- 从修改版 MiFlash 的压缩包内复制 **prog_ufs_firehose_sdm855_ddr.elf** 文件到线刷包的 `images` 文件夹内，并覆盖原本的文件。
- 在 **XiaoMiFlash** 内点击**选择**按钮并选择此文件夹。
- 点击**刷入**。
- 如果你得到了 `write time out` 错误，按住**电源键** + **音量上键**大概 30 秒左右来重启 EDL 模式。在这之后再次点击**刷入**按钮。

#### 重启你的设备
- 当它提示 **刷入完成**，按住**电源键**或**电源键** + **音量上键**大概 14 秒左右的时间来重启你的设备。


## 完成！















