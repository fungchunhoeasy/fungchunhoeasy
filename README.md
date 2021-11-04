# Edwardregen
sprov 这位大神开发的这套面板程序，很是方便，可以可视化的搭建SS、V2ray、Xray、Trojan等热门的协议，并且可以实时看到 VPS 的性能状态以及流量的使用情况。

那在经过将近两年的不断更新之后，V2-ui面板，迎来了一个比较大的转折——停止更新了。

sprov 大神又用 GO 语言重新开发了一套面板 X-UI。那这套面板相比原来的 V2-ui，兼容性更强，也便于维护， GO 语言的性能更好，而且内存占用也会相对的低一些。

#功能介绍

系统状态监控

支持多用户多协议，网页可视化操作

支持的协议：vmess、vless、trojan、shadowsocks、dokodemo-door、socks、http

支持配置更多传输配置

流量统计，限制流量，限制到期时间

可自定义 xray 配置模板

支持 https 访问面板（自备域名 + ssl 证书

#准备工作

VPS 一台重置好主流的操作系统 （CentOS 7+、Ubuntu 16+、Debian 8+）

域名一个，做好相关的解析，若是需要套用 CDN，请托管域名到 cloudflare。





下面环境的安装方式，大家根据自己的系统选择命令安装就好了。

#更新及安装组件


apt update -y          # Debian/Ubuntu 命令

apt install -y curl    #Debian/Ubuntu 命令

apt install -y socat    #Debian/Ubuntu 命令


#申请SSL证书

安装 Acme 脚本

curl https://get.acme.sh | sh

curl https://get.acme.sh | sh



80 端口空闲的证书申请方式

自行更换代码中的域名、邮箱为你解析的域名及邮箱

~/.acme.sh/acme.sh --register-account -m xxxx@xxxx.com

~/.acme.sh/acme.sh  --issue -d mydomain.com   --standalone



安装证书到指定文件夹

自行更换代码中的域名为你解析的域名

~/.acme.sh/acme.sh --installcert -d mydomain.com --key-file /root/private.key --fullchain-file /root/cert.crt

#安装 & 升级 X-ui 面板

bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
