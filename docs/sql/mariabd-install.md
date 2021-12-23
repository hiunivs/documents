---
sidebar_position: 1
---

# Debian安装配置MariaDB

MariaDB的API和协议兼容MySQL，另外又添加了一些功能，以支持本地的非阻塞操作和进度报告。这意味着，所有使用MySQL的连接器、库和应用程序也将会在MariaDB下工作。

## 安装

### 安装软件包

```bash
sudo apt update
sudo apt install mariadb-server
```

### 检查安装状态

```bash
sudo systemctr status mariadb
```

## 加固MariaDB

MariaDB内置有一个脚本，可以通过引导设置提高其安全性。

```bash
sudo mysql_secure_installation
```

根据提示设置

```bash
...
Enter current password for root (enter for none):
...
Set root password? [Y/n] Y
New password: 
Re-enter new password: 
...
Remove anonymous users? [Y/n] Y
...
Disallow root login remotely? [Y/n] Y
...
Remove test database and access to it? [Y/n] Y
...
Reload privilege tables now? [Y/n] Y
...
Thanks for using MariaDB!
```

## 登陆

```bash
mysql -u root -p
```
