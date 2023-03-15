# vps-shell
收集一些自用的shell脚本，适用于懒人使用。
## 一键网络重装
### DD Debian
` bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh') -d 10 -v 64 -p "自定义root密码" -port "22" `

参数说明 -d 10为 全新安装Debian10  -c 6为全新安装centos 6，其他依次类推
以下系统已通过测试:Debian: 9, 10, 11;Ubuntu: 18.04, 20.04;CentOS: 6,7;
以下平台已通过测试:Oracle(包括ARM)、Do、Azure

或者

`wget -O AutoReinstall.sh https://git.io/AutoReinstall.sh && bash AutoReinstall.sh`

Password: Pwd@Linux


### DD windows 7 (不支持甲骨文arm)
`wget -N --no-check-certificate https://raw.githubusercontent.com/veip007/dd/master/dd-gd.sh && chmod +x dd-gd.sh && ./dd-gd.sh` 
## BT面板开心版
### 专业版
`wget -O install.sh http://download.moetas.com/install/install-ubuntu_6.0.sh && bash install.sh`
### 企业版
`wget -O install.sh http://download.moetas.com/ltd/install/install-ubuntu_6.0.sh && bash install.sh`


## 流媒体检测
### 全面检测脚本
`bash <(curl -L -s https://raw.githubusercontent.com/lmc999/RegionRestrictionCheck/main/check.sh)`
### 简化版
`bash <(curl -sSL "https://github.com/CoiaPrant/MediaUnlock_Test/raw/main/check.sh")`

### 添加warp并解锁netflix 等流媒体
`bash <(curl -sSL https://raw.githubusercontent.com/fscarmen/warp_unlock/main/unlock.sh)`

## VPS跑分测试
### superbench
`wget -qO- git.io/superbench.sh | bash`
### Bench.sh
`wget -qO- bench.sh | bash`
### yabs 机器跑分
`curl -sL yabs.sh | bash`

### 三网测速
`bash <(curl -Lso- https://git.io/superspeed.sh)`
### 测试VPS基础信息，以及下载速度
`wget https://raw.githubusercontent.com/rptec/vps-shell/master/bench.sh && sh bench.sh`
### 跑分
`wget https://raw.githubusercontent.com/rptec/vps-shell/master/unixbench.sh && sh unixbench.sh`
## 回程网络
### 三网路由
`curl https://raw.githubusercontent.com/zhucaidan/mtr_trace/main/mtr_trace.sh|bash`


## Linux安装桌面
### 一键可浏览器访问的Linux桌面
`wget https://raw.githubusercontent.com/Har-Kuun/OneClickDesktop/master/OneClickDesktop_zh-CN.sh && sudo bash OneClickDesktop_zh-CN.sh`
### 一键安装声卡模拟
`wget https://raw.githubusercontent.com/Har-Kuun/OneClickDesktop/master/plugins/Audio/AudioRedirectionSetup.sh && sudo bash AudioRedirectionSetup.sh`

### xwindow
给你的linux装个桌面，适用于centos系统

`wget https://raw.githubusercontent.com/rptec/vps-shell/master/xwindow.sh && sh xwindow.sh`

## Linux docker-firefox
apt update -y ; apt upgrade -y
dpkg-reconfigure locales


```
docker pull lscr.io/linuxserver/firefox

docker run -d \
  --name=firefox \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Asia/Singapore \
  -p 3000:3000 \
  -v /path/to/config:/config \
  --shm-size="2gb" \
  --restart unless-stopped \
  lscr.io/linuxserver/firefox

```

## 加速
### 一键开启BBR
```
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
sysctl -p
sysctl net.ipv4.tcp_available_congestion_control
lsmod | grep bbr
```
### l2tp 一键包
一键安装l2tp的vpn服务器端，输入3个指令即可

`wget https://raw.githubusercontent.com/rptec/vps-shell/master/l2tp.sh && sh l2tp.sh`
### 锐速一键包
一键安装锐速破解全功能版，不支持openvz架构

`wget https://raw.githubusercontent.com/rptec/vps-shell/master/serverspeeder.sh && sh serverspeeder.sh`
### finalspeed 一键包
一键安装finalspeed功能，支持全系架构

`wget https://raw.githubusercontent.com/rptec/vps-shell/master/finalspeed.sh && sh finalspeed.sh`
### BBR  魔改版一键包
`wget https://raw.githubusercontent.com/rptec/vps-shell/master/bbr.sh && sh bbr.sh`
### 一键tcp加速 包括锐速及bbr暴力版等
`wget https://raw.githubusercontent.com/rptec/vps-shell/master/tcp.sh && sh tcp.sh`

## 一键docker
`curl -sSL https://get.docker.com/ | sh`

## 一键为VPS添加中文支持

`wget -N --no-check-certificate https://raw.githubusercontent.com/FunctionClub/LocaleCN/master/LocaleCN.sh && bash LocaleCN.sh`

## 一键为VPS添加Swap 虚拟内存

`wget https://raw.githubusercontent.com/rptec/vps-shell/master/swap.sh && sh swap.sh`

## 一键Warp 支持刷netflix解锁ip

`wget -N https://raw.githubusercontent.com/kkkyg/CFwarp/main/CFwarp.sh && bash CFwarp.sh`

## 一键Trojan go +ws

`bash <(curl -sL https://raw.githubusercontent.com/rptecs/vps-shell/master/trojangows.sh )`
