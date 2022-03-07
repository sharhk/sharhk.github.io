---
layout: post
title: WSL Graphic interface configuration
categories: [linux]
description: Open a graphic interface for wsl
keywords: wsl
---
### First time 
1 wsl --list --verbose 检查安装 wsl2

2 Windows 内下载vcXsrc并安装，XLaunch 配置后续提及

3 wsl 内安装xfce4 及 xubuntu-desktop
```bash
sudo apt install -y xfce4
sudo apt-get install xubuntu-desktop
```
4 配置wsl2 修改.bashrc 添加第二行语句
```bash
vim ~/.bashrc

%export DISPLAY=`cat /etc/resolv.conf | grep nameserver | awk '{print $2}'`:0

export DISPLAY=$(awk '/nameserver / {print $2; exit}' /etc/resolv.conf 2>/dev/null):0

source ~/.bashrc
```

5 启动配置Xlaunch
display settings: one large window； display number 0;
Extra Settings: check disable control access

6启动xfce4
```
startxfce4
```
 7 错误解决
 - connection time out;
 windows defender Firewall -> Allow an app for feature through Windows Defender Firewall, 找到vcXsrv 勾选
 
 ### 日常开启
 1 按照5 打开xlaunch 并配置
 2 wsl 中
 ``` 
 source ~/.bashrc
 startxfce4 
 ```
