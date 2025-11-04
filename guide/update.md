<img align="right" src="../media/raphaelbutnotass.png" width="350" alt="运行在 Redmi K20 Pro 上的 Windows 11">

# 在 Xiaomi Mi 9T Pro / Redmi K20 Pro 上运行 Windows

## 更新驱动

### 需要准备的文件
- [修改版 TWRP](https://github.com/new-WoA-Raphael/woa-raphael/releases/download/Files/modded-twrp-raphael.img)

- [驱动](https://github.com/new-WoA-Raphael/woa-raphael/releases/tag/Drivers)

- [UEFI 镜像](https://github.com/new-WoA-Raphael/woa-raphael/releases/tag/UEFI)

### 进入修改版 TWRP
> 在 fastboot 模式下，将 `path\to\modded-twrp-raphael.img` 替换为镜像所在的真实路径
> 
> 如果你无法访问 fastboot 模式的话，这里有一个临时的解决方法（但需要有自定义 recovery 提前安装）。你可以将当前的 boot 分区备份到电脑上，然后将修改版 TWRP 刷入 boot 分区并重启即可，后续恢复只需将备份的 boot 分区镜像刷入即可。
```cmd
fastboot boot path\to\modded-twrp-raphael.img
```

#### 运行 msc 脚本
> 如果提示让你再运行一遍，照做即可
```cmd
adb shell msc
```

### 运行 Diskpart
```cmd
diskpart
```

#### 选择手机上的 Windows 分区
> 使用 `list volume` 命令来找到它，将 "$" 替换为 **WINRAPHAEL** 的索引
```diskpart
select volume $
```

#### 分配字母 X
```diskpart
assign letter x
```

#### 退出 diskpart
```diskpart
exit
```

### 安装驱动
> [!Note]
> 此操作将会花费大约 20 分钟左右的时间。别担心，这很正常。

- 解压驱动压缩包，然后打开 `OfflineUpdater.cmd` 文件 (如果出现了错误，则运行 `OfflineUpdaterFix.cmd`)

> 如果它要求你输入一个字母，则输入 **WINRAPHAEL** 驱动器的盘符 (一般为 **X**)，然后回车

### Reboot your device
> Make sure to also change the UEFI image in Android, otherwise you may face a "blue screen of death" (BSoD) when booting Windows later.
```cmd
adb reboot
```

## Finished!













