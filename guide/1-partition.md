<img align="right" src="../media/raphaelbutnotass.png" width="350" alt="运行在 Redmi K20 Pro 上的 Windows 11">

# 在 Xiaomi Mi 9T Pro / Redmi K20 Pro 上运行 Windows

## 给你的设备分区

### 需要的东西
- 一个正常工作的大脑 (特别重要)
  
- 已解锁的 BL 锁
  
- 最好安装了最新版的固件
  
- [ADB 和 Fastboot 工具](https://developer.android.cn/studio/releases/platform-tools)
  
- [修改版 TWRP](https://gh.llkk.cc/https://github.com/new-WoA-Raphael/woa-raphael/releases/download/Files/modded-twrp-raphael.img)

### 注意
> [!WARNING]  
> 所有的数据都将被清除！如果需要的话请立即备份。
> 
> 不要多次运行同一个命令。
> 
> **不要重启你的手机！**如果你认为你做错了某一步，请前往 [Telegram 聊天](t.me/woaraphael)来寻求帮助。
> 
> 不要一次执行所有指令，按顺序执行它们！

> [!IMPORTANT]
> 确保在整个教程的过程中都使用修改版的 TWRP，因为我们在其中内置了一些工具能让安装过程更轻松一些。
> 
> 如果你没有使用它并遇到了任何错误，请将其认定为你自己的错误并由于会被认为脱离了主教程则需自行解决。

### 以管理员身份运行命令提示符
> 下载 **platform-tools** 并解压到某处，然后以**管理员**身份打开命令提示符。
>
> 推荐保持这个窗口打开并在整个教程的过程中使用同一个命令行窗口。
> 
> 将 `path\to\platform-tools` 替换为你将其解压到的路径，例如 **C:\platform-tools**.
```cmd
cd path\to\platform-tools
```

### 启动到修改版 TWRP
> 在 fastboot 模式下，将 `path\to\modded-twrp-raphael.img` 替换为镜像所在的真实路径
> 
> 如果你无法访问 fastboot 模式的话，这里有一个临时的解决方法（但需要有自定义 recovery 提前安装）。你可以将当前的 boot 分区备份到电脑上，然后将修改版 TWRP 刷入 boot 分区并重启即可，后续恢复只需将备份的 boot 分区镜像刷入即可。
```cmd
fastboot boot path\to\modded-twrp-raphael.img
```

#### 备份你的 boot 镜像
> 如果你无法访问 fastboot 模式并按照了临时的解决方法，则你可以跳过这一步。
> 
> 这将会把你的 boot 分区镜像备份到当前目录 (也就是 **platform-tools** 文件夹)
>
> 如果提示 "no devices/emulators found" 则重新插拔线缆并重试
```cmd
adb pull /dev/block/by-name/boot boot.img
```

### 给你的设备分区
> 目前有两种方法来给你的设备分区。请在下方选择一种你喜欢的方法。

#### 方法 1: 手动分区 

<details>
  <summary><strong>点击此处查看方法 1</strong></summary> 

#### 打开一个 adb 终端
```cmd
adb shell
```

#### 重新设置分区表大小
```cmd
sgdisk --resize-table 64 /dev/block/sda
```

### 准备分区
$${\color{lightblue}🟦 注意}$$
> 如果在任何时候你从 Parted 中看到了一个错误提示并让你选择 "Yes/No" 或 "Ignore/Cancel"，请根据情况输入 `Yes` 或 `Ignore` 来忽略错误并继续。
>
> 如果你看到了任何带有 **udevadm** 的错误，那么你也可以忽略掉那些。
```cmd
parted /dev/block/sda
```

#### 查看当前的分区表
> 执行此指令后 Parted 会输出当前的分区表，userdata 分区则应该在分区表的最后
```cmd
print
``` 

#### 删除 userdata 分区
> 将 **$** 替换为 **userdata** 分区的索引，一般是 **31**
```cmd
rm $
``` 

#### 重新创建 userdata 分区
> 将 **2080MB** 替换为刚刚删除的 **userdata** 分区的扇区初始值
>
> 将 **64GB** 替换为你想要的 **userdata** 分区的扇区结束值。在这个例子中安卓的可用空间将为 64GB-2080MB = **62GB**
```cmd
mkpart userdata ext4 2080MB 64GB
``` 

#### 创建 ESP 分区
> 将 **64GB** 替换为刚刚创建的 **userdata** 分区的扇区结束值
>
> 将 **64.3GB** 替换为上一个参数加 **0.3GB** 的值
```cmd
mkpart esp fat32 64GB 64.3GB
``` 

#### 创建 Windows 分区
> 将 **64.3GB** 替换为 **esp** 分区的扇区结束值
```cmd
mkpart win ntfs 64.3GB -0MB
``` 

#### 将 ESP 分区设置为可引导
> 使用 `print` 命令查看分区表。将 "$" 替换为 ESP 分区的索引，一般是 **32**
```cmd
set $ esp on
``` 

#### 退出 parted
```cmd
quit
``` 

### 格式化 data 分区
- 在 TWRP 里格式化 data 分区，否则安卓系统不会启动。
- ( 前往擦除 > 格式化 data 分区 > 输入 yes ) 

#### 检查安卓系统是否能正常启动
- 重启你的手机并查看安卓系统是否还能工作
- 如果你使用的是上面提到的临时解决方案，则将备份的 boot 分区镜像用 TWRP 刷入到 boot 分区并重启即可

### 格式化 Windows 和 ESP 分区
> 重新回到修改版 TWRP，然后运行下面两条命令
```cmd
adb shell mkfs.ntfs -f /dev/block/by-name/win -L WINRAPHAEL
``` 

```cmd
adb shell mkfs.fat -F32 -s1 /dev/block/by-name/esp -n ESPRAPHAEL
``` 

### 修复 GPT 分区表
> 如果你不这么做，Windows 可能会损坏你的设备
```cmd
adb shell fixgpt
```

</details>

#### 方法 2: 自动分区

<details>
  <summary><strong>点击此处查看方法 2</strong></summary> 

> [!Important]
> 如果你的设备使用动态分区或更新的 rom，**不要使用自动分区脚本！**请使用**方法 1: 手动分区**。

### 运行分区脚本
> 将 **$** 替换为你想要 Windows 所拥有的空间大小 (不需要在结尾加上 GB，直接填写数字即可)
> 
> 如果它要求你再运行一次，照做即可
```cmd
adb shell partition $
``` 

### 检查安卓系统是否能正常启动
- 重启你的手机并查看安卓系统是否还能工作
- 如果你使用的是上面提到的临时解决方案，则将备份的 boot 分区镜像用 TWRP 刷入到 boot 分区并重启即可

</details>

## [下一步: 获取 Root 权限](/guide/2-root.md)















