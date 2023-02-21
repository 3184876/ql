# 一键脚本一键脚本
收集一些自用的shell脚本。

## yabs测试脚本yabs测试脚本

`wget -qO- yabs.sh | bash`
来自GitHub，老外比较爱用的服务器性能测试脚本。

## SuperBench性能和国内网络测试

`bash <(wget -qO-  http://tutu.ovh/bash/superbench/superbench.sh)`
来自于LOC MJJ，测试内容完整方便。

## 服务器回程路由测试

`wget --no-check-certificate https://tutu.ovh/bash/returnroute/route && chmod +x route && clear && ./route`
或者
`curl http://tutu.ovh/bash/returnroute/test.sh|bash`
来自李子博客，适用于centos6/7，测试服务器回程线路类型是否为CN2网络。

## NextTrace路由追踪

`bash <(curl -Ls https://raw.githubusercontent.com/sjlleo/nexttrace/main/nt_install.sh)`
`Example：nexttrace 8.8.8.8`
来自于@sjlleo开源的路由测试程序，支持多个查询接口，不受IPIP.NET的限制。

## NALI纯真IP版本

`rpm -ivh http://tutu.ovh/bash/nali/nali-chunzhen-1.0.1-3.x86_64.rpm`
更新地址库可以使用nali-update命令,IP库更新地址：https://tutu.ovh/bash/nali/QQWry.Dat 
来自李子博客，适用于centos7，集成了纯真IP库的nali，用于各种场景解析ip归属地。

## OLINK AS9929 GRE隧道复用脚本

`wget tutu.ovh/bash/olink-mgre/mgre;chmod +x mgre`
用法如下：
创建olink隧道    : ./mgre olink
移除olink隧道    : ./mgre olink_remove
创建转发节点任务 : ./mgre forward {隧道名称} {转发服务器隧道IP} {转发服务器公网IP} {待优化服务器隧道IP} {待优化服务器公网IP}
移除转发节点任务 : ./mgre forward_remove {隧道名称}
创建客户端任务   : ./mgre client {隧道名称} {转发服务器隧道IP} {转发服务器公网IP} {待优化服务器隧道IP} {待优化服务器公网IP}
移除客户端任务   : ./mgre client_remove
实验功能: 由于AS9929价格昂贵,您可以选择仅优化小包. 小包场景包括:访问网页/远程连接/DNS请求/网络游戏, 文件下载/在线视频/数据传输 等大包场景则走普通线路.
启用小包分流模块 : ./mgre client_rules_add
移除小包分流模块 : ./mgre client_rules_remove
测试大小包回程路由 : ./mgre client_traceroute
来自李子博客，用于服务器网络速度优化，需自行购买OLINK CLOUD官方套餐。适用于centos7，其他操作系统暂不支持。注意本程序请勿与锐速/Lotserver一同使用，推荐使用兼容性更好的bbr。

## TCPA一键包

`wget http://tutu.ovh/tcp_opz/tcpa/tcpa.sh`
`sh tcpa.sh`
来自李子博客,适用centos7，tcp单边加速组件，用于服务器网络优化，自动更换内核并重启自动安装，源于腾讯内部TEG内核团队。

## CLOUDFLARE IPV4回源白名单脚本

`wget http://tutu.ovh/bash/cloudflare-whitelist/cf.sh`
`sh cf.sh`
注意：执行后会自动移除防火墙80和443端口的放行规则！
来自李子博客，适用centos7，用于cloudflare加速时自动维护防火墙源站白名单，使用前请自行启用firewalld防火墙。

## FUNCDN IPV4回源白名单脚本

`wget https://tutu.ovh/bash/funcdn-whitelist/funcdn.sh`
`sh funcdn.sh`
注意：执行后会自动移除防火墙80和443端口的放行规则！
来自李子博客，适用centos7，用于funcdn加速时自动维护防火墙源站白名单，使用前请自行启用firewalld防火墙。

## 流媒体区域检测（仅NETFLIX）

AMD64
`wget --no-check-certificate -O nf https://github.com/sjlleo/netflix-verify/releases/download/v3.1.0-1/nf_linux_amd64 && chmod +x nf && clear && ./nf`
ARM64
`wget --no-check-certificate -O nf https://github.com/sjlleo/netflix-verify/releases/download/v3.1.0-1/nf_linux_arm64 && chmod +x nf && clear && ./nf`
来自GitHub开源社区，用于Netflix可用区域检测，支持CentOS 6+, Ubuntu 14.04+, Debian 8+。

## 流媒体区域检测

`bash <(curl -L -s check.unlock.media)`
来自GitHub开源社区，所有流媒体可用区域检测,支持CentOS 6+, Ubuntu 14.04+, Debian 8+, MacOS, Android (Termux), iOS (iSH)。

## OPENSSL一键自签证书

`bash <(curl -sL tutu.ovh/bash/onekeyssl/ssl.sh)`
一键生成任意期限的IP/域名自签证书。

## IPTABLES端口中转

`http://tutu.ovh/zjzx/shell/iptables-pf.sh`
iptables端口中转加速远程桌面、酸酸、ssh连接等,适用于centos 6。

## html5网速程序

`http://tutu.ovh/zjzx/shell/speedtest.zip`
需要php环境，下载后解压即可运行，无须安装

## 锐速一键包

`rpm -ivh http://tutu.ovh/kernel/lotserver/old/centos7/kernel-3.10.0-229.1.2.el7.x86_64.rpm --force`
`reboot`
`bash <(wget --no-check-certificate -qO- http://tutu.ovh/bash/lotserver/Install.sh) install`
锐速tcp单边加速，用于服务器网络优化。更换内核，一键安装锐速。

## GoogleBBR一键脚本

`http://tutu.ovh/zjzx/shell/bbr.sh`
bbr tcp单边加速，用于服务器网络优化，google出品的拥塞算法。一键安装并开启bbr功能，不支持openvz虚拟架构。

## FS一键包

`http://tutu.ovh/zjzx/shell/finalspeed.sh`
一键安装finalspeed功能，支持全系架构

## 自动备份脚本

`http://tutu.ovh/zjzx/shell/AutoBackupToFtp.sh`
每天自动备份MYSQL及打包网站目录

## 使用方法

`wget --no-check-certificate https://tutu.ovh/zjzx/shell/name.sh`
`chmod +x name.sh`
`./name.sh`
