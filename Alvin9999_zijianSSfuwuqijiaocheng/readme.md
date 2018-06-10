vultr账号注册链接：     https://www.vultr.com/?ref=7224941



本脚本需要Linux root账户权限才能正常安装运行，所以如果不是 root账号，请先切换为root，如果是 root账号，那么请跳过！

sudo su

输入上面代码回车后会提示你输入当前用户的密码，输入并回车后，没有报错就继续下面的步骤安装ShadowsocksR。


一键部署ssr代码(虽然代码兼容SS客户端，但最好用SSR客户端，因为SSR客户端可以用SSR混淆协议）如下：

apt-get install -y aptitude

aptitude install -y wget

wget --no-check-certificate https://raw.githubusercontent.com/Turing2333/SSR_server_build_script_backup/master/Alvin9999_zijianSSfuwuqijiaocheng/morenjiamifangshihehunxiao/ssr.sh

chmod +x ssr.sh

./ssr.sh 2>&1 | tee ssr.log

———————————————————代码分割线————————————————

上面这个代码是默认的加密方式和混淆协议，没法自行修改加密方式和混淆协议，如果有这方面的需求，可以用下面这个脚本

Debian/Ubuntu/Deepin ShadowsocksR单/多端口一键管理脚本：

apt-get install -y wget

wget -N --no-check-certificate https://raw.githubusercontent.com/Turing2333/SSR_server_build_script_backup/master/Alvin9999_zijianSSfuwuqijiaocheng/CentOS_Debian_Ubuntu_SSR_danduoduankouyijianguanlijiaoben/ssr.sh && chmod +x ssr.sh && bash ssr.sh

脚本内容：

支持 限制 端口限速

支持 限制 端口设备数

支持 显示 当前连接IP

支持 显示 SS/SSR连接+二维码

支持 切换管理 单/多端口

支持 一键安装 BBR

支持 一键安装 锐速

支持 一键安装 LotServer

支持 一键封禁 垃圾邮件(SMAP)/BT/PT

下载运行后会提示你输入数字来选择要做什么。

安装脚本后，以后只需要运行这个命令就可以进行设置：bash ssr.sh

之后输入对应的数字来执行相应的命令。

界面如下：

安装 ShadowsocksR

更新 ShadowsocksR

卸载 ShadowsocksR

安装 libsodium(chacha20)

————————————


查看 账号信息

显示 连接信息

设置 用户配置

手动 修改配置

切换 端口模式

————————————


启动 ShadowsocksR

停止 ShadowsocksR

重启 ShadowsocksR

查看 ShadowsocksR 日志

————————————


其他功能

升级脚本

当前状态: 已安装 并 已启动 当前模式: 单端口

请输入数字(1-15)：

最后重启服务器确保部署生效。重启需要在命令栏里输入reboot ，输入命令后稍微等待一会服务器就会自动重启，一般重启过程需要2～5分钟，重启过程中Xshell会自动断开连接（比如：你用qq远程你朋友的电脑，但他的电脑突然重启了，你这边自然就掉线了），等VPS重启好后，再用Xshell连接一下即可。

如果部署失败，卡在某个位置，可以用xshell软件断开，然后重新连接你的ip，再复制代码进行部署。



一键加速VPS服务器

此加速教程为谷歌BBR加速和破解版锐速加速教程，两者只能成功装一个，都仅支持KVM框架的vps服务器，vultr的服务器都是KVM框架。如果你购买的不是vultr的服务器，那么你需要搞清楚你买的vps服务器是否是KVM框架的，很重要。（vultr的服务器装谷歌bbr）

按照第二步的步骤，重新连接服务器ip，登录成功后，在命令栏里粘贴以下代码：

【谷歌BBR加速教程】

apt-get install -y wget

wget --no-check-certificate https://raw.githubusercontent.com/Turing2333/SSR_server_build_script_backup/master/Alvin9999_zijianSSfuwuqijiaocheng/GoogleBBRjiasu/bbr.sh

chmod +x bbr.sh

./bbr.sh

最后输入y重启服务器或者手动输入代码reboot


【锐速加速教程】

apt-get install -y wget

wget -N --no-check-certificate https://raw.githubusercontent.com/Turing2333/SSR_server_build_script_backup/master/Alvin9999_zijianSSfuwuqijiaocheng/ruisujiasu/serverspeeder-all.sh && bash serverspeeder-all.sh

把上面整个代码复制后粘贴进去。该方法是开机自动启动，部署一次就可以了。但有些内核是不适合的，部署过程中需要手动选择推荐的

提示没有完全匹配的内核,随便选一个内核就行,按照提示来输入数字,按回车键即可

锐速安装成功标志为出现running字样。
