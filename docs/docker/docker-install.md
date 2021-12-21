---
sidebar_position: 2
---

# Docker安装

## 删除旧版本

```shell
sudo apt remove docker docker-engine docker.io containerd runc
```

## 安装Docker

### 使用官方仓库安装

#### 设置仓库

1.设置仓库：

```shell
sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

2.添加Docker官方GPG key:

```shell
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

3.Use the following command to set up the stable repository. To add the nightly or test repository, add the word nightly or test (or both) after the word stable in the commands below. Learn about nightly and test channels.

```shell
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### 安装Docker Engine

1.Update the apt package index, and install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:

```shell
 sudo apt-get update

 sudo apt-get install docker-ce docker-ce-cli containerd.io
```

2.To install a specific version of Docker Engine, list the available versions in the repo, then select and install:

a.List the versions available in your repo:

```shell
apt-cache madison docker-ce
```

b.Install a specific version using the version string from the second column, for example , 5:18.09.1~3-0~ubuntu-xenial.

```shell
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```

3.Verify that Docker Engine is installed correctly by running the hello-world image.

```shell
sudo docker run hello-world
```
