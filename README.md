# shadowsocksR
Using SSR to Scientify Internet Access

如果你想访问国外的网站的话，这个时候就需要科学上网，这里做下步骤记录。

**:shipit:ShadowsocksR 科学上网原理**

>SSR从本质上来说是一种加密代理方式，其服务端搭建在国外VPS服务器上，客户端在用户终端设备上。服务器做为中间桥梁，使我们间接访问国外网站。同时由于是加密代理，防火墙无法识别访问内容，访问比较安全。

![](https://github.com/Lumnca/shadowsocksR/blob/master/img/2018-07-24_161526.png)

***

**SSR的搭建步骤**

从前文的简图中，我们可以大概了解到SSR的搭建步骤：

* 1.购买1台国外VPS服务器。
* 2.在服务器上安装SSR服务端。
* 3.在本地电脑或手机等设备上，安装SSR客户端并与服务端连接，OK。

是不是也没那么难？下面我们会分步详细介绍，按照下面的步骤，看完你就能享受自己的SSR科学上网啦！:smirk:	

***

**1.购买国外VPS服务器**

>关于价格，其实并不贵国外的VPS服务器贵其实并不贵，一般来说，512M内存的服务器就足够我们搭建SSR了，年付价格一般在20-30美元，平均下来一个月只需十几块人民币，一碗面而已。即使是主流的1G内存服务器，月付最多才5美元。关于支付，可用支付宝上面说起国外服务器、美元，很多朋友可能觉得很遥远、很麻烦，其实不是这样，很多大牌商家支持支付宝付款，或者Paypal付款。付款时，美元会自动转换为人民币，与我们日常网购没两样。


用哪家的服务器，怎么购买
推荐搬瓦工或Vultr：

[搬瓦工](https://bwh88.net/cart.php?gid=1)

[Vultr](https://my.vultr.com)

远程连接服务器工具一般可以用XShell（远程控制台）和Xftp（远程ftp文件上传）

[Xshell/Xftp下载](https://xshell.en.softonic.com/)

**2.服务器上安装SSR服务端**

>SSR服务器端的安装，也很简单，有一键安装脚本支持，安装过程做几个选择就可以了

安装脚本为服务器端使用，即SSR服务端一键安装。服务器系统：`CentOS6及以上、Debian7及以上、Ubuntu12`及以上系统内存支持128M及以上，推荐256M起步。

* 1.在电脑端打开Xshell，连接VPS服务器，以root用户登录。
* 2.登录成功后，依次运行以下三条命令：

```shell
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
```

```shell
chmod +x shadowsocks-all.sh
```

```shell
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```
（小提示：如果运行上面第一条命令时，出现找不到wget之类的提示，则表明系统没有预装wget，先运行以下命令完成wget的安装）

```
CentoS系统：
yum -y install wget 

Ubuntu/Debian系统：
apt-get -y install wget
```

![](https://github.com/Lumnca/shadowsocksR/blob/master/img/HFT2FEJMSC67YHXN%7BJM%5B%5BUQ.png)

![](https://github.com/Lumnca/shadowsocksR/blob/master/img/KTR%60JCQZL%7B8S%60U1YTB9WAWO.png)

![](https://github.com/Lumnca/shadowsocksR/blob/master/img/_YR%25QX%7DJ0~~%7BSB1Y%24V%5B%5D9~T.png)



SSR服务端安装成功后，就可以在电脑、手机、路由器等设备上的SSR客户端上，按照以上设置的各项参数进行连接了。

常用命令

```
启动SSR：
/etc/init.d/shadowsocks-r start
退出SSR：
/etc/init.d/shadowsocks-r stop
重启SSR：
/etc/init.d/shadowsocks-r restart
SSR状态：
/etc/init.d/shadowsocks-r status
卸载SSR：
./shadowsocks-all.sh uninstall
```

