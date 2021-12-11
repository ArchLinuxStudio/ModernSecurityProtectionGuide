# 匿名支付

在一些全面实行实名制且对国民进行全方位监视的国家，在网络中几乎任何支付方式都会留下与你真实身份相关的信息，匿名支付方式是非常有必要掌握学习的。我们建议你使用虚拟货币进行交易。

首先出现的问题是 交易所和钱包 的选择。交易所自身往往也提供钱包，但是很多都需要各类身份、支付方式认证。除此之外，交易所是中心化托管方式，用户的资产实际上为交易所所持有，所以不推荐使用交易所的钱包。对于独立的虚拟货币钱包，又分为硬件钱包和软件钱包，也即冷热钱包（一种特殊的硬件钱包:打印在纸类上的[纸钱包](https://bitcoinpaperwallet.com/)，本文不讨论）。冷钱包的安全性更好是毋庸置疑的，较为知名的冷钱包有[Ledger](https://www.ledger.com/)以及[Trezor](https://shop.trezor.io/)。它们的相关软件可在 archlinux 上通过如下命令安装。其中 ledger-live 是开源软件。

```bash
yay -S ledger-live
yay -S trezor-suite-appimage
```

在安装本文所述软件时，如遇 gpg no name 错误，均可通过更换 server 的方式解决

```bash
gpg --keyserver hkp://keyserver.ubuntu.com --recv-keys TARGET_FINGERPRINT
```

购买冷钱包存储大额货币可以获得更好的安全性，但是相对来说它并没有软件钱包方便。一般来说软件钱包同时支持更多的币种，且交易更方便，具体的选择则需要用户根据自身需求自行决定。

软件钱包也有众多选择，从匿名钱包以及 Linux 平台使用的角度考虑，[Guarda](https://guarda.com/)、[Wasabi](https://wasabiwallet.io/)、[Electrum](https://electrum.org/) 以及 [Exodus](https://www.exodus.com/) 是较好的选择。其中 Wasabi 和 Electrum 是开源软件。这些软件钱包在使用时均不需要提供邮箱或者手机进行注册，同时如 Wasabi 还内置了 Tor 网络，而 Guarda 和 Exodus 则更易于使用。理论上讲，无论是软件钱包还是硬件钱包相关的软件，它们都应该开源以保证绝对的安全可信，但目前来讲，在这个领域内方便好用的开源钱包软件很难找到。它们可在 archlinux 上通过如下命令安装。

```bash
yay -S guarda-appimage
yay -S wasabi-wallet-bin
yay -S electrum-appimage
yay -S exodus
```

Ref:

- [Guarda 钱包评测](https://cn.bitdegree.org/crypto/guarda-qianbao-pingce)
- [Exodus 钱包评测](https://cn.bitdegree.org/crypto/exodus-qianbao-pingce)
- [best-anonymous-bitcoin-wallets](https://bitcoinafrica.io/best-anonymous-bitcoin-wallets/)
