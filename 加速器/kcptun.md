**:rocket:KCPTUN加速**

>KCPTUN是一款服务器双边加速工具，可以将服务器的TCP流量，比如Shadowsokcs/Shadowsocksr的流量，转化为KCP协议的UDP流量发出。
作为一款暴力发包工具，KCPTUN可以有效解决丢包问题，明显提升传输速度，是站长目前用过的效果最为突出的加速工具。

KCPTUN的优点：

* 1.不挑服务器平台，OpenVZ、KVM、Xen等虚拟化架构都支持。
* 2.基本不挑系统，Linxu下的CentOS、Debian、Ubuntu等都可以安装。
* 3.加速效果明显，可以避开TCP流量的QOS限速，减少拥堵。
* 4.使用KCPTUN对SSR流量加速后，访问Google/Youtube等网站时，可以达到接近秒开的效果，这一点表现比BBR/锐速更好一些。

KCPTUN的缺点：

* 1.需要KCPTUN服务器端和客户端配合使用。
* 2.参数配置项较多，可能需要多次尝试不同的参数搭配，从而获得最佳效果。下文会提供一些常用搭配。
* 3.由于是暴力发包，KCPTUN可能会耗费成倍的服务器流量，还会影响到服务器上的邻居。
* 4.只能加速单一端囗的TCP流量，对其余端囗的TCP流量无加速效果，所以常用于SS/SSR加速。

>下面我们介绍下KCPTUN服务器端的安装，本一键脚本来自kuoruan。
适用平台：OpenVZ、KVM、Xen等。
适用系统：CentOS、Debian、Ubuntu等Linux发行版。

依次执行下面3条命令

```
wget --no-check-certificate https://github.com/kuoruan/shell-scripts/raw/master/kcptun/kcptun.sh
chmod +x ./kcptun.sh
./kcptun.sh
```
