---
sidebar_position: 2
---

# Debian/Ubuntu使用代理服务

如何在Linux下正常使用代理服务的相关内容.

## bash下使用代理连接

由于网络原因导致某些软件的安装、更新等比较慢，可以使用代理来加速。如：系统更新、npm依赖的更新等。在bash下运行命令时最好使用的代理服务是ProxyChains。

ProxyChains是Linux和其他Unix下的代理工具。 它可以使任何程序通过代理上网， 允许TCP和DNS通过代理隧道， 支持HTTP、 SOCKS4和SOCKS5类型的代理服务器， 并且可配置多个代理。 ProxyChains通过一个用户定义的代理列表强制连接指定的应用程序， 直接断开接收方和发送方的连接。

ProxyChains 是一个强制应用的 TCP 连接通过代理的工具，支持 Tor、HTTP、与 Socks 代理。与 sshuttle 不同的是，ProxyChains 只会将当前应用的 TCP 连接转发至代理，而非全局代理。所以我们可以在bash下使用ProxyChains对命令进行单独的代理。

### 安装

```bash
sudo apt install proxyChains
```

### 修改配置文件

ProxyChains 的配置文件位于 /etc/proxychains.conf ，打开后你需要在末尾添加你使用的代理。例如：

```shell
[ProxyList]
# add proxy here ...
# meanwile
# defaults set to "tor"
#socks4  127.0.0.1 9050
socks5 127.0.0.1 1080
```

***注意：你添加的代理必须是正常运行的代理，此处的`socks5 127.0.0.1 1080`是我本机运行的一个代理服务。具体如何搭建代理服务非此处讨论的内容。***

### 使用

ProxyChains的使用十分简单，只需要在任何你需要运行的命令前加上`proxyChains`就可以。

比如：

```shell
[ProxyList]
# 在 Ubuntu 上更新软件包
sudo proxychains apt update

# 安装 npm 依赖
sudo proxychains npm install

# 使用 docker
sudo proxychains docker run helloworld
```

***注意：由于proxychains只会代理TCP，所以对于使用UDP或者ICMP协议的命令则无效。比如使用`ping`命令则不会走代理服务。***

## 代理客户端
