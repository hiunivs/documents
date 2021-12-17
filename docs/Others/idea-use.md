---
sidebar_position: 2
---

# IntelliJ IDEA使用

## Debian/Ubuntu安装JetBrains IDE

### 使用snap安装

对于Ubuntu可以直接使用Snap安装Pycharm、Idea、Phpstorm和Clion

```shell
#安装pycharm-professional
sudo snap install pycharm-professional --classic
#安装pycharm-community
sudo snap install pycharm-community --classic

#安装idea-community
sudo snap install intellij-idea-community --classic
#安装idea-ultimate
sudo snap install intellij-idea-ultimate --classic
#安装idea-educational
sudo snap install intellij-idea-educational --classic

#安装idea-phpstorm
sudo snap install phpstorm --classic

#安装clion
sudo snap install clion --classic
```

### 使用二进制包安装

- 下载Linux对应的安装包  
PyCharm：`https://www.jetbrains.com/pycharm/download/#section=linux`  
IntelliJ `IDEA：https://www.jetbrains.com/idea/download/#section=linux`  
Goland：`https://www.jetbrains.com/go/download/#section=linux`  
PhpStorm：`https://www.jetbrains.com/phpstorm/download/#section=linux`  
CLion：`https://www.jetbrains.com/clion/download/#section=linux`  

- 解压安装包到安装目录

```shell
#此处以Goland为例
sudo tar -C /usr/local -xzf goland-2021.3.tar.gz
```

- 启动IDE

```shell
cd /usr/local/GoLand-2021.3/bin
sudo ./goland.sh
```

## 使用技巧

### 代码自动换行

#### 临时换行

在显示行数的位置右侧空白处右击，勾选 Soft-Wrap，则该文件就实现了代码自动换行。

#### 所有同一格式的文件均自动换行

在”File-Settings-Editor-General-Soft Wrap“下Soft-wrap these files中添加需要自动换行的文件类型，如：*.md(全部的md文件)。

### 修改内存大小

根据实际情况调整允许的内存大小，打开`Help-Edit Custom VM Options`，修改`-Xmx****m`，其中`****m`表示允许的内存大小。修改之后重启IDE即可。

### 创建桌面快捷方式

打开程序之后通过`Tools-Create desktop entry`可以直接创建快捷方式。

***在创建快捷方式的对话框中建议勾选`Create the entry for all users`选项。***
