# I2P

I2P（Invisible Internet Project 即“隐形网计划”）,I2P 网络是由 I2P 路由器以大蒜路由方式组成的表层网络，创建于其上的应用程序可以安全匿名的相互通信。其应用包括匿名上网、聊天、撰写博客和文件传输。

与 Tor 相比，其链路更加多样可变，可以提供更强的匿名性，但是在其网络内内容相对 Tor 较少。

## 安装使用

ArchLinux 上可以安装 c++实现的[i2pd](https://archlinux.org/packages/community/x86_64/i2pd/)或者原版[i2p](https://aur.archlinux.org/packages/i2p/)。本文描述原版 i2p 的使用，因为其功能更易于使用。

安装结束后，enable 并 start `i2prouter.service`。打开浏览器，在`127.0.0.1:7657`即可看到初始化向导，按照提示进行即可。I2P 提供 HTTP 代理在 4444 端口，可以在你需要使用的软件，如浏览器中设置 HTTP 代理。

## 配置工作

### 补种

首先要进行的工作是补种，补种是一个网络引导过程，用于发现其他路由，首次安装 I2P 仅有很少路由信息故需要补种。在[此页面](http://127.0.0.1:7657/configreseed)进行补种。由于威权政府往往进行网络封锁，在此页面的下方的补种设置中，需要设置代理进行有效补种。将你的 HTTP 代理主机和端口填入后，点击`保存修改并立刻开始补种`，等待至多数十分钟后即可在页面左侧的竖边栏的`节点`部分，看到有数十的活动节点。

### 带宽

随后进行增加带宽的工作，在[此页面](http://127.0.0.1:7657/config)进行操作。将入站出站以及共享比率按你的实际情况加大，可改善 I2P 网络速度。共享的带宽越多，匿名性就越强，同时能帮助 I2P 网络成长。

### 地址簿

接下来进行地址簿的添加,I2P 内部的网站需要路由才能进行访问。进入[此页面](http://localhost:7657/susidns/subscriptions),将如下内容填入，并点击保存，等待一阵即可。

```txt
http://i2p-projekt.i2p/hosts.txt
http://notbob.i2p/hosts-all.txt
http://notbob.i2p/hosts.txt
http://skank.i2p/hosts.txt
http://stats.i2p/cgi-bin/newhosts.txt
```

### outproxy

最后需要更改 outproxy 以对 I2P 外部网络(如 google)、以及洋葱路由域进行访问。打开[此页面](http://localhost:7657/i2ptunnel/)，在下方的`I2P 客户端隧道`一节中，点击`I2P HTTP Proxy`的设置按钮，将`出口代理`以及`SSL出口代理`从原有的 false.i2p 改为 purokishi.i2p。最后保存即可。

## 意义

首先 I2P 可以提供和 Tor 类似的匿名网络以供使用。其次，在你所掌握的翻墙手段全部失效时，一个配置好的 I2P 可以帮助你暂时应急访问互联网。I2P 网络本身提供的众多应用功能是其最主要的部分，如邮箱，论坛，代码仓库，博客等等，使用这些内部应用，你将相当安全。

---

Ref:

- [I2P wikipedia](https://zh.wikipedia.org/wiki/I2P)
- [The easiest way to get the most out of I2P: Update your subscription lists and change your outproxy.](http://smv3cryi3n7d5ll7xpvlhstubi5yj4dadeltyrdwdr4onwd2jvvq.b32.i2p/f/I2P/629/the-easiest-way-to-get-the-most-out-of-i2p-update-your)
- [Arch wiki I2P](https://wiki.archlinux.org/title/I2P)
- [编程随想: 简单扫盲 I2P 的使用](https://program-think.blogspot.com/2012/06/gfw-i2p.html)
- [I2P 匿名网络使用扫盲](https://blog.jimmyho.net/archives/562/)
- [i2pd 折腾心得](https://johnrosen1.com/2021/01/28/i2p/)
- [高级科学上网—i2p-匿名-暗网[适用于 pc 安卓 linux]](https://www.feiyu01.com/8016.html)
- [I2P 的终极指南以及如何安装和使用它](https://dementium2.com/vpn-2/i2p/#I2P_vs_Tor_vs_Freenet)
- [I2P 不完全使用手册](https://www.williamlong.info/archives/2696.html)
- [匿名网络 Tor 与 I2P 关键技术研究](https://m.hanspub.org/journal/paper/31299)
- [匿名网络 Tor 与 I2P 的比较研究](http://www.infocomm-journal.com/cjnis/article/2019/2096-109x/2096-109x-5-1-00066.shtml)
