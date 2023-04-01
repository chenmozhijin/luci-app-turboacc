# luci-app-turboacc
一个兼容官方openwrt(22.03) firewall4的turboacc
包括以下功能：软件流量分载、Shortcut-FE、全锥型 NAT、BBR 拥塞控制算法


##需要的依赖/䃼丁
Shortcut-FE需要：
[ fast-classifier、shortcut-fe、simulated-driver ](https://github.com/coolsnowwolf/lede/tree/master/package/lean/shortcut-fe)、[ 952-net-conntrack-events-support-multiple-registrant.patch ](https://github.com/coolsnowwolf/lede/blob/master/target/linux/generic/hack-5.10/952-net-conntrack-events-support-multiple-registrant.patch)、[953-net-patch-linux-kernel-to-support-shortcut-fe.patch](https://github.com/coolsnowwolf/lede/blob/master/target/linux/generic/hack-5.10/953-net-patch-linux-kernel-to-support-shortcut-fe.patch)

全锥型 NAT需要：[nft-fullcone](https://github.com/fullcone-nat-nftables/nft-fullcone)、[982-add-bcm-fullconenat-support.patch](https://github.com/coolsnowwolf/lede/blob/master/target/linux/generic/hack-5.10/982-add-bcm-fullconenat-support.patch)并为新的“fullcone”语句修补firewall4、libnftnl和nftables

修补firewall4、libnftnl和nftables需要：
[firewall4 patch](https://github.com/wongsyrone/lede-1/blob/master/package/network/config/firewall4/patches/999-01-firewall4-add-fullcone-support.patch)、
[nftables patch](https://github.com/wongsyrone/lede-1/blob/master/package/network/utils/nftables/patches/999-01-nftables-add-fullcone-expression-support.patch)与
[libnftnl patch](https://github.com/wongsyrone/lede-1/blob/master/package/libs/libnftnl/patches/999-01-libnftnl-add-fullcone-expression-support.patch)或[firewall4修补的存储库](https://github.com/wongsyrone/openwrt-firewall4-with-fullcone)、[nftables修补的存储库](https://github.com/wongsyrone/nftables-1.0.2-with-fullcone)与[libnftnl修补的存储库](https://github.com/wongsyrone/libnftnl-1.2.1-with-fullcone)

如果编译22.03.3则可以使用 https://github.com/chenmozhijin/turboacc/tree/package

编译全锥型 NAT很麻烦并容易编译出错如果要编译请先阅读[Nftables 全锥型 NAT实现](https://github.com/Chion82/netfilter-full-cone-nat/issues/42)


