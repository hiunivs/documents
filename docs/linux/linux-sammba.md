---
sidebar_position: 1
---

# Debian/Ubuntu安装使用Samba

Samba是一个功能强大的开源工具，它允许在Linux系统上的网络中像Windows一样共享文件和打印机，它使Linux和Windows机器可以在同一网络上共存和交互。它安装在托管Linux的服务器上这些文件将被共享。这些共享的文件可被同一网络上的任何授权Linux或Windows客户端访问。

## Samba安装

```bash
sudo apt install samba
```

## 验证安装

Samba安装后启动的服务是 `nmbd`，可以通过产看其状态确认samaba是否正常启动。

```bash
sudo systemctr status nmbd
```

## 配置Samba

samba配置文件smb.conf位于 `/etc/samba` 在此文件中，我们指定要共享的文件夹和打印机以及它们的权限和操作参数.Samba会在一段时间后检查其配置文件并更新所有更改。

### 创建samba用户

```bash
sudo smbpasswd -a samba
#输入两次密码
#本用户用于samba登陆之用
```

### 编辑配置文件

```bash
sudo vi /etc/samba/smb.conf
```

```bash
[share]
   comment = share on Debian
   path = /mnt/share
   public = yes
   valid users = samba
   writable = yes
   create mask = 0660
   directory mask = 0775
```

### 重新启动samba服务

```bash
sudo systemctl restart smbd.service
```
