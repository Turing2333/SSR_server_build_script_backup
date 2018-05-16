vultr账号注册链接： https://www.vultr.com/?ref=7224941



# Ubuntu包更新

sudo apt install aptitude && sudo aptitude full-upgrade && sudo reboot


# 单独给ShadowsocksR服务端指定DNS

此方法适合给ShadowsocksR服务端单独设置一个DNS服务器。

假设你的ShadowsocksR服务端安装在 /root 目录中，那么：

ShadowsocksR根目录(多用户)，即目录为 /root/shadowsocksr/

ShadowsocksR子目录(单用户)，即目录为 /root/shadowsocksr/shadowsocks

根据当前在使用的单用户/多用户方式，来选择在对应的目录下新建 dns.conf 文件，格式如下：

8.8.8.8 53

8.8.4.4 53

每行一个DNS服务器，端口为 53 时，可忽略不写。

可以用 vi / nano 来新建/编辑，也可以用 echo 命令直接写入，比如：

根目录
echo -e "8.8.8.8 53

8.8.4.4 53" > /root/shadowsocksr/dns.conf

子目录
echo -e "8.8.8.8 53

8.8.4.4 53" > /root/shadowsocksr/shadowsocks/dns.conf

此方法具有最高优先级，当ShadowsocksR服务端启动时会检测目录下是否有 dns.conf 文件，如果有并格式正确，那就会直接读取这个DNS配置，而不会读取系统的DNS配置。


# 修改系统默认的DNS

Ubuntu的默认DNS配置文件为： /etc/resolv.conf

修改内容 格式如下：

nameserver 1.1.1.1

nameserver 8.8.8.8

可以用 vi / nano 来新建/编辑，也可以用 echo 命令直接写入，比如：

systemctl stop systemd-resolved
systemctl disable systemd-resolved
echo -e "nameserver 1.1.1.1
nameserver 8.8.8.8" > /etc/resolv.conf

此方法仅支持53端口，不需填写端口号。

此方法具有次级优先级，当ShadowsocksR服务端目录下没有 dns.conf 文件时，ShadowsocksR便会读取这个系统默认的DNS。


以上两种方法修改DNS后，都需要重启ShadowsocksR服务端才能生效。

服务端启动时会显示所使用的DNS，可通过查看日志来确定是否生效。






