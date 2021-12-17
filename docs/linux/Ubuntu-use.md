---
sidebar_position: 1
---

# 在Debian/Ubuntu使用

### 对于Firefox浏览器播放部分网站的视频报错
对于部分网站的视频无法播放，提示`to play video you may need to install the required video codecs`，其主要原因是系统没有安装部分视频解码器(video codecs)，可以通过安装相关解码器解决；
```shell
sudo apt install ubuntu-restricted-extras
```
***你可能需要重新启动浏览器才可以正常使用。***