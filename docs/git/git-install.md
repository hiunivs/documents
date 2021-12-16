---
sidebar_position: 2
---

# Git安装

## Git安装
### Linux下安装
Linux下可以通过源码编译安装，也可以直接使用软件包管理软件安装二进制包。使用软件包管理软件安装更加的方便，我建议直接使用这种安装方式。

对于Debian及Ubuntu使用 ```apt``` 进行安装
```shell
sudo apt install git
```

对于CentOS使用 ```yum``` 进行安装
```shell
sudo yum install git
```
对于其它Linux发行版或者Unix发行版的安装命令参考[Git官方安装步骤](https://git-scm.com/download/linux)。

### macOS下安装
在macOS下安装Git有两种安装方式，一种是通过安装 Xcode Command Line Tools附带安装Git，另一种是使用二进制安装程序进行安装。

**通过 Xcode Command Line Tools进行安装**
```shell
#运行该命令后根据提示进行安装
git --version
```

或
```shell
#运行该命令直接安装
xcode-select --install
```

**使用二进制安装程序进行安装**

- 使用Homebrew安装
```shell
#运行该命令后根据提示进行安装
brew install git
```
- 使用图形化安装程序安装

下载链接为：https://sourceforge.net/projects/git-osx-installer/
### Windows下安装
Windows下的安装有多种方式，最简单的安装方式是使用 Git for Windows安装程序进行安装。你也可以通过Chocolatey安装。另一个方式是通过安装GitHub Desktop获得。

***Windows下推荐使用Git for Windows安装程序进行安装。***

**Git for Windows**

下载地址为：https://git-scm.com/download/win

**Chocolatey安装**
```shell
#在PowerShell命令行下运行
choco install git
```
使用该方式安装需要你的电脑已经安装Chocolatey包管理软件，如果未安装的话可以使用下述命令进行安装：
```shell
#安装Chocolatey
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
**安装GitHub Desktop获得**

下载地址为：https://desktop.github.com/

## git和git-all安装的区别的区别
git-all包含所有子包，而git仅包含具有最小依赖性的主要组件。 git-all安装时除了安装git及其相关依赖之外会额外安装下述组件：
- git-doc（git文档，无依赖项的10.8 MiB）
- git-cvs（git-cvs互操作性，没有依赖项的1.1 MiB）
- git-mediawiki（MediaWiki远程帮助器，0.8 MiB，没有依赖项）
- git-svn（git-svn互操作性，没有依赖项的1.0 MiB）
- git-email（git电子邮件附件，0.8 MiB，无依赖项）
- git-gui（git GUI，2.2 MiB不依赖）
- gitk（git版本树可视化器，1.5 MiB，无依赖项）
- gitweb（git Web界面，0.8 MiB，无依赖项）

可以参考Debian Packages上两包的依赖情况：
- [git相关依赖](https://packages.debian.org/sid/git)
- [git-all相关依赖](https://packages.debian.org/sid/git-all)

:::tip
如果只在命令行下使用Git，建议只安装git，如果需要其它附加组件，比如GUI，则可以安装git-all。日常使用来说基本只使用到git核心功能，较少使用附加组件功能。
:::