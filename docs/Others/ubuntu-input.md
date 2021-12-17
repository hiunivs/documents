---
sidebar_position: 1
---

# Ubuntu输入相关

## 输入法

### 安装Google输入法

第一步：安装Fcitx框架

```shell
sudo apt install fcitx
```

第二步：配置Fcitx

```shell
im-config
```

在弹出窗口中选择fcitx

***注意：设置结束后需要重启系统。***

第三步：安装Google输入法

```shell
sudo apt install fcitx-googlepinyin
```

第四步：配置Google输入法

```shell
fcitx-config-gtk3
```

在设置中添加Google Pinyin

***注意：如果找不到Google Pinyin则可能需要重启系统后再进行设置。***

### Google输入法快捷键

- 繁体和简体转换快捷键：ctrl + shift + F
- 中英文切换：shift
- 输入法切换：ctrl + space

***正常情况下使用ctrl + space切换到Google输入法后可以直接使用shift键切换中英文，但是部分情况下会出现无法正常切换的情况。可以说时好时坏。***

## 使用问题

### JetBrains IDE使用中文输入法

在部分情况下使用Ubuntu默认的ibus输入时会出现中文无法正常输入的情况，可以使用下述方法解决：

```text
  点击菜单 "Help | Edit Custom VM options..."
  添加 -Drecreate.x11.input.method=true 到最后一行
  重启IDEA
```

### JetBrains IDE使用中文输入法输入框不跟随

在JetBrains IDE中使用中文输入法时输入框是不能跟随光标的，会出现在左下角，具体原因是JetBrains IDE在安装时打包了自己的OpenJDK，而这个运行时存在bug导致这一问题，解决的办法就是修改并替换有问题的运行时。

### Ubuntu英文系统添加中文输入

安装Ubuntu英文系统后默认是没有中文输入法的，可以通过系统设置添加，具体步骤如下：

- Settings-Region & Language-Manage Installed Languages
- 上一步点击结束后会自动安装中文语言
- 在Input Sources中点击“+”号，选择Chinese，选择你想要添加的输入法（使用全拼可以选择Intelligent Pinyin）。

## 个人使用建议

我个人不太习惯复杂的操作，喜欢输入法一直处于中文输入法，在需要输入英文时使用左sheft健直接切换。所以尝试了Ubuntu系统自带的ibus框架下的智能全拼和fcitx框架下的Google Pinyin输入法。

就个人习惯来说更偏向于使用ibus，不过由于其与JetBrains IDE存在兼容问题，所以需要在JetBrains IDE中进行设置，经过重新设置后暂时未出现兼容问题。具体设置参见[JetBrains IDE使用中文输入法](#jetbrains-ide使用中文输入法)

使用Google Pinyin输入法存在一个致命的问题就是其快捷键在切换中英文时会时效，为找到具体解决办法，所以最终放弃使用。这个问题只是对于我使用习惯影响较大，对于习惯中英文切换直接切换语言的用户应该没有影响，你可以直接切换到英文输入法。
