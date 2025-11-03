<img align="right" src="https://github.com/new-WoA-Raphael/woa-raphael/blob/main/media/raphaelbutnotass.png" width="350" alt="Windows 11 running on a Redmi K20 Pro">

# 在 Xiaomi Mi 9T Pro / Redmi K20 Pro 上运行 Windows

## 实现 Android 和 Windows 无缝双系统启动

### 需要准备的文件
- [UEFI 镜像](https://github.com/new-WoA-Raphael/woa-raphael/releases/tag/UEFI)

- [WOA 助手 app](https://github.com/n00b69/woa-helper/releases/tag/APK)

## 设置双系统启动软件
> 这个指南默认认为你已经取得了 root 权限，如果你还没有 root，请先遵循[这个指南](root.md)。

### 设置 - Android 端
- 下载并安装 **WOA 助手** app，然后打开它并授予其 root 权限。
- 下载 **UEFI 镜像**并将其放在你的内部存储中一个名为 `UEFI` 的文件夹。
- 打开 WOA 助手并点击**WOA 工具箱**，然后在弹出的页面中点击**STA CREATOR**。
> [!Important]
> If `/sdcard/Windows` is empty, your rom does not support mounting and you will have to make a boot.img backup inside the app, then copy it manually to Windows once you boot to it (for example by uploading it somewhere and then downloading it while booted into Windows). The same applies to the StA files, which are also generated in your internal storage.
>
> Do the same thing if the folder is read-only.
- Press the **QUICKBOOT TO WINDOWS** button.

### Setup - Windows
> [!Tip]
> If this is your first time booting Windows and you wish to skip the Microsoft Account login, press the **I don't have internet** button in the WiFi page, then when prompted, press the **Continue with limited setup** button.
>
> If there is no such button, press the **SIM card** button at the top of the screen (the one that says **Connected**), and press **Disconnect**.
- Navigate to `C:\sta` and create a shortcut of **sta.exe** to your desktop, if one isn't already present

#### Booting to Android
- Run the new shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

#### Booting to Windows
- Press **QUICKBOOT TO WINDOWS** inside the app, or use the newly created toggle in your quick settings panel

> [!Important]
> If you ever update or change your Android ROM, make sure to create a new **boot.img** backup (after rooting your phone!) and place it inside the **C:\ folder** in Windows, overwriting the old file.
>
> You can use the **BACK UP BOOT IMAGE** feature in the WOA Helper app to do so.

## Finished!









