<img align="right" src="https://github.com/new-WoA-Raphael/woa-raphael/blob/main/media/raphaelbutnotass.png" width="350" alt="Windows 11 running on a Redmi K20 Pro">

# 在 Xiaomi Mi 9T Pro / Redmi K20 Pro 上运行 Windows

## 故障排除
> 下发你可以找到一些常见的问题及其解决方案

## 无法在 Android 系统内挂载 Windows 分区
如果挂载 Windows 产生了一个空文件夹，说明你要么没安装 Windows，要么是你的 rom 包不支持挂载分区。

##### 完成！


## 无法在 Android 里向 Windows 分区写入文件
> 这是由于在 Windows 内选择了关机而不是重启。
- 要解决这个问题，先启动到 Windows 内然后点击“重启”，当屏幕黑掉的那个时候启动到 TWRP 并从那里加载进入 Android。
- 或关闭 Windows 的休眠功能。
> 再或者，如果你已经在 Windows 里设置好了切换到 Android 的那个软件，只需使用它来进入 Android 即可。

##### 完成！


## Charging in Windows does not work
> [!WARNING]
> Do not use a powered USB hub with host mode enabled, this can potentially break your device. If you use a powered USB hub, please use the [disable USB host mode guide](/guide/English/Additional-materials-en.md#Disabling-USB-host-mode)

Charging in Windows only works on specific cables. Cables that have been known to work are the original Poco X3 Pro cable (identified by the additional orange/red pin in the USB-A port), and the Nimaso 100W USB-C to USB-C fast charging cable.

##### Done!


## Device can boot into Android but not bootloader
> This is caused by having partitions with a name longer  than 16 characters, such as **Basic data partition**, which has 20 characters
- Reboot to the modded recovery and in the built-in terminal run
```cmd
parted /dev/block/sda
```
- Run ```print``` to list all partitions
- Look for partitions that are more than 16 characters long, for example "Basic Data Partition" and note their volume number
- Rename this partition with ```name $ test```, replacing **$** with the partition number, and replacing **test** with the name you want the partition to have
- Run ```quit```
- Reboot to bootloader in the reboot menu to check if fastboot works again

##### Done!




















