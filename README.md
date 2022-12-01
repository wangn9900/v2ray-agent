# make-a大神八合一一键安装脚本（克隆版，原作者已删库）
支持快捷方式启动，安装完毕后，shell输入【 vasma 】即可打开脚本，脚本执行路径[ /etc/v2ray-agent/install.sh ]
Latest Version【推荐】
# ssh后台输入以下命令
```
wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/wangn9900/v2ray-agent/main/install.sh" && chmod 700 /root/install.sh && /root/install.sh
```
# 特性
* <br>支持[Xray-core[XTLS]](https://github.com/XTLS/Xray-core)、v2ray-core 
* <br>支持切换前置[VLESS XTLS -> Trojan XTLS]、[Trojan XTLS -> VLESS XTLS]
* <br>支持不同核心之间的配置文件互支持 VLESS/VMess/tr支持Debian、Ubuntu、Centos，支持主流的cpu架构。不建议使用Centos以及低版本的系统，2.3.x后不再支持Centos6
* <br>支持个性化安装
* <br>支持多用户管理
* <br>支持Netflix检测、支持DNS流媒体解锁、支持任意门解锁Netflix
* <br>无需卸载即可安装、重装任意组合
* <br>支持卸载时保留Nginx、tls证书。如果acme.sh申请的证书在有效的情况下，不会重新签发
* <br>支持纯IPv6，IPv6注意事项
* <br>支持IPv4[入]->IPv6分流[出]
* <br>支持WARP分流
* <br>支持日志管理
* <br>支持多端口配置
* <br>支持自定义证书安装
# 支持的安装类型
* VLESS+TCP+TLS
* VLESS+TCP+xtls-rprx-direct【 推荐 】
* <br>VLESS+gRPC+TLS【支持CDN、IPv6、延迟低】 
* <br>VLESS+WS+TLS【支持CDN、IPv6】 
* <br>Trojan+TCP+TLS【 推荐 】   
* <br>Trojan+TCP+xtls-rprx-direct【 推荐 】 
* <br>Trojan+gRPC+TLS【支持CDN、IPv6、延迟低】 
* <br>VMess+WS+TLS【支持CDN、IPv6】
# 组合推荐中转/gia/AS4837/AS9929 ---> VLESS+TCP+TLS/XTLS、Trojan【推荐使用XTLS的xtls-rprx-direct】
移动宽带 ---> VMESS+WS+TLS/VLESS+WS+TLS/VLESS+gRPC+TLS/Trojan+gRPC+TLS + Cloudflare
cloudflare-> VLESS+gRPC+TLS/Trojan+gRPC+TLS[多路复用、延迟低]
# 注意事项
修改Cloudflare->SSL/TLS->Overview->Full
Cloudflare ---> A记录解析的云朵必须为灰色【如非灰色，会影响到定时任务自动续签证书】
如用CDN又同时使用直连，关闭云朵+自选IP，自选IP参考上方的Cloudflare 优化方案
使用纯净系统安装，如使用其他脚本安装过，请重新build系统再安装
wget: command not found [ 这里需要自己手动安装下wget ]
，如未使用过Linux，点击查看安装教程
不支持非root账户
中间的版本号升级意味可能不兼容之前安装的内容，如果不是追新用户或者必须升级的版本请谨慎升级。 例如 2.2.，不兼容2.1.
如发现Nginx相关问题，请卸载掉自编译的nginx或者重新build系统
为了节约时间，反馈请带上详细截图或者按照模版规范，无截图或者不按照规范的issue会被直接关闭
不建议GCP用户使用
不建议使用Centos以及低版本的系统，如果Centos安装失败，请切换至Debian10重新尝试，脚本不再支持Centos6、Ubuntu 16.x
如有使用不明白的地方请先查看脚本使用指南
Oracle vps有一个额外的防火墙，需要手动设置
Oracle vps仅支持Ubuntu
如果使用gRPC通过cloudflare转发,需要在cloudflare设置允许gRPC，cloudflare Network->gRPC
gRPC目前处于测试阶段，可能对你使用的客户端不兼容，如不能使用请忽略
