# vps-shell
收集一些自用的shell脚本，适用于懒人使用。
## 一键网络重装
### DD Debian
` bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh') -d 10 -v 64 -p "自定义root密码" -port "22" `

以下系统已通过测试:
Debian: 9, 10, 11;
Ubuntu: 18.04, 20.04;
CentOS: 6,7;
以下平台已通过测试:
Oracle(包括ARM)、Do、Azure

### DD windows 7 (不支持甲骨文arm)
` 
wget --no-check-certificate -qO InstallNET.sh 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh' && bash InstallNET.sh -dd 'http://d.nat.ee/win/lite/win7-ent-sp1-x64-cn/win7-ent-sp1-x64-cn.vhd.gz'`


### 开机改密并开启root权限
适用于GCP, AZURE,甲骨文等
```
#!/bin/bash
echo root:passwd |sudo chpasswd root
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;
sudo reboot
```

## BT面板开心版

### 专业版
`wget -O install.sh http://download.moetas.com/install/install-ubuntu_6.0.sh && bash install.sh`
### 企业版
`wget -O install.sh http://download.moetas.com/ltd/install/install-ubuntu_6.0.sh && bash install.sh`


## 流媒体检测脚本
` wget https://raw.githubusercontent.com/rptec/vps-shell/master/check.sh && sh check.sh ` 



## 服务器三网下载（上传）速度脚本
wget https://raw.githubusercontent.com/rptec/vps-shell/master/superspeed.sh && sh superspeed.sh

## 一键tcp加速
包括锐速及bbr暴力版等

wget https://raw.githubusercontent.com/rptec/vps-shell/master/tcp.sh && sh tcp.sh


## VPS测试
测试VPS基础信息，以及下载速度

wget https://raw.githubusercontent.com/rptec/vps-shell/master/bench.sh && sh bench.sh

跑分

wget https://raw.githubusercontent.com/rptec/vps-shell/master/unixbench.sh && sh unixbench.sh

## Linux安装桌面

给你的linux装个桌面，适用于centos系统

wget https://raw.githubusercontent.com/rptec/vps-shell/master/xwindow.sh && sh xwindow.sh
## SS 一键包
一键安装shadowsocks服务器端，python版本，适用一切linux系统

wget https://raw.githubusercontent.com/rptec/vps-shell/master/shadowsocks.sh && sh shadowsocks.sh

## SSR 一键包
wget https://raw.githubusercontent.com/rptec/vps-shell/master/shadowsocksR.sh && sh shadowsocksR.sh

# 加速

## 一键开启BBR
```
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
sysctl -p
sysctl net.ipv4.tcp_available_congestion_control
lsmod | grep bbr
```
## l2tp 一键包
一键安装l2tp的vpn服务器端，输入3个指令即可
wget https://raw.githubusercontent.com/rptec/vps-shell/master/l2tp.sh && sh l2tp.sh

## 锐速一键包

一键安装锐速破解全功能版，不支持openvz架构

wget https://raw.githubusercontent.com/rptec/vps-shell/master/serverspeeder.sh && sh serverspeeder.sh

## finalspeed 一键包

一键安装finalspeed功能，支持全系架构
wget https://raw.githubusercontent.com/rptec/vps-shell/master/finalspeed.sh && sh finalspeed.sh

## BBR  魔改版一键包
wget https://raw.githubusercontent.com/rptec/vps-shell/master/bbr.sh && sh bbr.sh


