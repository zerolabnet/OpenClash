### Description

OpenClash compiled without `kmod-inet-diag` dependence. For users who're using the version which does not have `kmod-inet-diag` in the repository.

### My changes

In the "Small Flash Memory" mode, the `rule_provider` folder has been moved to tmpfs since v0.45.22-beta.

### Install dependencies

```bash
opkg update
opkg install dnsmasq-full --download-only && opkg remove dnsmasq && opkg install dnsmasq-full --cache . && rm *.ipk
```
##### If you have iptables:
```bash
opkg install wget-ssl coreutils-nohup bash iptables curl ca-certificates ipset ip-full iptables-mod-tproxy iptables-mod-extra libcap libcap-bin ruby ruby-yaml kmod-tun unzip luci-compat
```

##### If you have nftables:
```bash
opkg install wget-ssl coreutils-nohup bash curl ca-certificates ipset ip-full libcap libcap-bin ruby ruby-yaml kmod-tun unzip kmod-nft-tproxy luci-compat
```

### Install OpenClash

```bash
cd /tmp
wget https://github.com/zerolabnet/OpenClash/releases/download/v0.45.112-beta/luci-app-openclash_0.45.112-beta_all.ipk
opkg install luci-app-openclash_0.45.112-beta_all.ipk
```
