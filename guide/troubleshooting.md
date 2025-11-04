<img align="right" src="../media/raphaelbutnotass.png" width="350" alt="运行在 Redmi K20 Pro 上的 Windows 11">

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


## Windows 内无法充电
> [!Warning]
> 不要在启用了主机模式后使用带供电的 USB 拓展坞，这可能会损坏你的设备。如果你正在使用带有供电的 USB 拓展坞，请查看[如何关闭 USB 主机模式](/guide/English/Additional-materials-en.md#Disabling-USB-host-mode)

在 Windows 中充电只对特定线缆可用。例如 Poco X3 Pro 原装的充电线 (通过查看 USB-A 口中的橙/红色针脚来识别)，和 Nimaso 100W USB-C to USB-C 快充线。

##### 完成！


## 设备可以进入 Android 但无法进入 bootloader
> 这是由于某个分区名称超过了 16 个字符导致的，例如 **Basic data partition**（基础数据分区）有 20 个字符
- 重启到修改后的 TWRP 内并使用内置终端运行
```cmd
parted /dev/block/sda
```
- 运行 ```print``` 来查看分区列表
- 查看是否有分区名称超过了 16 个字符的分区，例如 "Basic Data Partition" 并记住它们的卷编号
- 使用命令 ```name $ test``` 重命名分区，将 **$** 替换为卷编号，并将 **test** 替换为你想要的分区名
- 运行 ```quit```
- 在重启菜单中重启到 bootloader 来查看 fastboot 是否可用

##### 完成！




















