vultr账号注册链接： https://www.vultr.com/?ref=7224941

本脚本需要Linux root账户权限才能正常安装运行，所以如果不是 root账号，请先切换为root，如果是 root账号，那么请跳过！

sudo su
输入上面代码回车后会提示你输入当前用户的密码，输入并回车后，没有报错就继续下面的步骤安装ShadowsocksR。

注意：如果你安装的有我的另一个 ssr.sh 脚本，请先卸载ShadowsocksR服务端，再安装这个脚本（不能共存）！

apt-get install -y aptitude

aptitude install -y wget

wget -N --no-check-certificate https://raw.githubusercontent.com/Turing2333/SSR_server_build_script_backup/master/ShadowsocksR_MudbJSON_moshi_duoyonghuyijianjiaoben_zhichiliuliangxianzhideng/ssrmu.sh && chmod +x ssrmu.sh && bash ssrmu.sh

注意：关于限制设备数数，这个协议必须是非原版并且不兼容原版才有效，也就是必须SSR客户端使用协议的情况下，才有效！

使用说明

运行脚本，

bash ssrmu.sh

# 还有一个 运行参数，是用于所有用户流量清零的
bash ssrmu.sh clearall
# 不过不需要管这个，可以通过脚本自动化的设置 crontab 定时运行脚本
输入对应的数字来执行相应的命令。

  ShadowsocksR MuJSON一键管理脚本 [vX.X.X]
  ---- Toyo | doub.io/ss-jc60 ----

  1. 安装 ShadowsocksR
  2. 更新 ShadowsocksR
  3. 卸载 ShadowsocksR
  4. 安装 libsodium(chacha20)
————————————
  5. 查看 账号信息
  6. 显示 连接信息
  7. 设置 用户配置
  8. 手动 修改配置
  9. 清零 已用流量
————————————
 10. 启动 ShadowsocksR
 11. 停止 ShadowsocksR
 12. 重启 ShadowsocksR
 13. 查看 ShadowsocksR 日志
————————————
 14. 其他功能
 15. 升级脚本

 当前状态: 已安装 并 已启动

请输入数字 [1-15]：
注意：添加/删除/修改 用户配置后，无需重启ShadowsocksR服务端，ShadowsocksR服务端会定时读取数据库文件内的信息，不过修改 用户配置后，可能要等个十几秒才能应用最新的配置（因为ShadowsocksR不是实时读取数据库的，所以有间隔时间）。
文件位置

安装目录：/usr/local/shadowsocksr

配置文件：/usr/local/shadowsocksr/user-config.json

数据文件：/usr/local/shadowsocksr/mudb.json

注意：ShadowsocksR服务端不会实时的把流量数据写入 数据库文件，所以脚本读取流量信息也不是实时的！
其他说明

ShadowsocksR 安装后，自动设置为 系统服务，所以支持使用服务来启动/停止等操作，同时支持开机启动。

启动 ShadowsocksR：service ssrmu start
停止 ShadowsocksR：service ssrmu stop
重启 ShadowsocksR：service ssrmu restart
查看 ShadowsocksR状态：service ssrmu status
ShadowsocksR 默认支持UDP转发，服务端无需任何设置。

本脚本已经集成了 安装/卸载 锐速(ServerSpeeder)/Lotserver，但是是否支持请查看 Linux支持内核列表 。（锐速、LotServer不支持OpenVZ）



注意：本脚本中的 显示链接信息中的 获取IP归属地功能使用的是 IPIP.NET 的免费API接口，因为限速所以每秒只能检测一次，同时 IPIP.NET 的免费API接口并不会保证稳定性，可能什么时候就突然暂时失效了，这是本人不可控的，有条件可以自建API接口。

定时重启

一些人可能需要定时重启ShadowsocksR服务端来保证稳定性等，所以这里用 crontab 定时。


crontab -e
# 首先打开定时设置，然后会出现文本编辑，按 I键 进入编辑模式，根据需求添加下下面的代码到 这个文本编辑框内！！
------------
# 如果提示命令不存在，那么安装crontab：
# CentOS系统：
yum update
yum install -y crond
# Debian/Ubuntu系统：
apt-get install -y aptitude
aptitude install -y cron
安装并打开 crontab 后，我们根据需求添加下面的代码，添加后我们按 ESC键 退出编辑模式，然后输入 :wq 保存并退出。

# 添加定时重启任务
# 是添加到 crontab -e 文本编辑框内，而不是让你执行！
# 下面代码前面的 * * * * * 分别对应：分钟 小时 日 月 星期

10 2 * * * /etc/init.d/ssr restart
# 这个代表 每天2点10分重启一次 ShadowsocksR

10 2 */2 * * /etc/init.d/ssr restart
# 这个代表 每隔2天的2点10分重启一次 ShadowsocksR

10 */4 * * * /etc/init.d/ssr restart
# 这个代表 每隔4小时的第10分重启一次 ShadowsocksR

一键加速VPS服务器

此加速教程为谷歌BBR加速和破解版锐速加速教程，两者只能成功装一个，都仅支持KVM框架的vps服务器，vultr的服务器都是KVM框架。如果你购买的不是vultr的服务器，那么你需要搞清楚你买的vps服务器是否是KVM框架的，很重要。（vultr的服务器装谷歌bbr）

按照第二步的步骤，重新连接服务器ip，登录成功后，在命令栏里粘贴以下代码：

【谷歌BBR加速教程】

apt-get install -y aptitude

aptitude install -y wget

wget --no-check-certificate https://raw.githubusercontent.com/Turing2333/SSR_server_build_script_backup/master/Alvin9999_zijianSSfuwuqijiaocheng/GoogleBBRjiasu/bbr.sh

chmod +x bbr.sh

./bbr.sh

最后输入y重启服务器或者手动输入代码reboot

【锐速加速教程】

apt-get install -y aptitude

aptitude install -y wget

wget -N --no-check-certificate https://raw.githubusercontent.com/Turing2333/SSR_server_build_script_backup/master/Alvin9999_zijianSSfuwuqijiaocheng/ruisujiasu/serverspeeder-all.sh && bash serverspeeder-all.sh

把上面整个代码复制后粘贴进去。该方法是开机自动启动，部署一次就可以了。但有些内核是不适合的，部署过程中需要手动选择推荐的

提示没有完全匹配的内核,随便选一个内核就行,按照提示来输入数字,按回车键即可

锐速安装成功标志为出现running字样。
