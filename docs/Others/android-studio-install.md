---
sidebar_position: 3
---

# Android Studio 安装及使用教程

## 安装Android Studio

### 安装依赖库

如果运行的是Debian/Ubuntu 64位的系统需要安装部分32位的依赖库：

```shell
sudo apt-get install libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 libbz2-1.0:i386
```

### 安装AS

- 下载Linux对应的安装包  
下载地址：`https://developer.android.com/studio`

- 解压安装包到安装目录

```shell
sudo tar -C /usr/local -xzf android-studio-2020.3.1.26-linux.tar.gz
```

- 启动IDE

```shell
cd /usr/local/android-studio/bin
sudo ./studio.sh
```

- 创建桌面快捷方式

打开程序之后通过`Tools-Create desktop entry`可以直接创建快捷方式。

***在创建快捷方式的对话框中建议勾选`Create the entry for all users`选项。***
