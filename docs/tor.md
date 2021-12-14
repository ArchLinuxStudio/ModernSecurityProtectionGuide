# Tor

关于 Tor 的文章数不胜数，本文不再赘述，只需要记住使用 Tor 可大幅提高上网的隐匿性与安全性。如果你对 Tor 一无所知，可以先阅读[Tor 浏览器用户手册](https://tb-manual.torproject.org/zh-CN)。下文描述在 ArchLinux 上 Tor 的使用方式，以及注意事项。[Arch Wiki - Tor](https://wiki.archlinux.org/title/Tor)

安装如下软件包

```bash
yay -S tor tor-browser
```

使用 Tor 的方式大致分为两种：直接用 Tor 浏览器、以及启动 Tor 独立服务供其他应用使用。实际上 Tor 浏览器也会启动 Tor 服务，只是其还提供了一个整合的浏览器便于使用。

---

如果你在一个民主自由的国家，Tor 一般不需要任何额外设置即可使用。除此之外，你还可以使用 Tor 浏览器的内置网桥方案(如 obfs4、meek。obfs4 是远程网桥、meek 是本地网桥)进一步提升网络访问的隐匿性，用于混淆、规避审查。除此之外，这些内置网桥方案还有另外的附属作用，那就是可以突破互联网封锁(翻墙)。在独裁、威权政府统治的国家中，Tor 网络几乎被完全封锁、阻止访问。使用这些内置网桥方案可以帮助你在网络被封锁和审查的情况下顺利连接到 Tor 网络。

如果你在一个独裁威权的国家，Tor 是被严格封锁的。除了上述的使用内置网桥方案连接至 Tor 网络，还可以使用[全局代理](https://archlinuxstudio.github.io/ArchLinuxTutorial/#/advanced/transparentProxy)或者[单独代理](https://archlinuxstudio.github.io/ArchLinuxTutorial/#/rookie/fxckGFW)的方式来连接至 Tor。

> 需要注意的是，使用代理连接 Tor 网络时，需要禁用 TLS 嗅探功能[[1]](https://github.com/v2ray/discussion/issues/49)。

如果你想要其他应用程序也可以使用 Tor,则将其代理配置中的值设置为 Tor 服务运行的端口号即可。

运营商和监听者是可以确认谁在使用 Tor 流量的，但是其无法确定访问的网址。尽可能提高 Tor 的普及和使用人数，有助于提高所有人的隐匿性。同时，如果部署很精密的流量分析系统，是有一定可能对应网站访问者和 Tor 使用者的，使用前置代理配合 Tor 的多重代理方式可以进一步提升隐匿性。如果你处在 Tor 被完全封锁的国家，如中国，前置的代理是必须添加的，因为 Tor 流量是可以被监听者和 ISP 检测到的，如果通过网桥直连，那么盖世太保们和 ISP 很明显的可以看到可能一个区一个市只有某几处有 Tor 流量，这是非常危险的。由于 Tor 在这些国家被完全封锁，用户肯定比其他 Tor 没有被封锁的国家少非常非常多，所以一旦有 Tor 流量就极为显眼。

无论如何，不论是普通代理还是 Tor 网络，其入口的第一个节点是一定可以获取到你的真实 IP 的，确保这个节点的安全、匿名和可信是必要的，这也是为什么前文所说机场不够安全的原因。

- [编程随想:Tor 的常见问题](https://program-think.medium.com/%E5%A6%82%E4%BD%95%E7%BF%BB%E5%A2%99-%E7%B3%BB%E5%88%97-%E5%85%B3%E4%BA%8E-tor-%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94-daa1115ac300)
- [Tor community](https://community.torproject.org/)
- [Tor FAQ](https://support.torproject.org/zh-CN/faq/)
