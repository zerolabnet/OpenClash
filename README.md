### Description

OpenClash without `kmod-inet-diag` dependence.

### Install dependencies

```bash
opkg update
opkg install dnsmasq-full --download-only && opkg remove dnsmasq && opkg install dnsmasq-full --cache . && rm *.ipk
opkg install wget-ssl coreutils-nohup bash iptables curl ca-certificates ipset ip-full iptables-mod-tproxy iptables-mod-extra libcap libcap-bin ruby ruby-yaml kmod-tun luci-compat
```

### Install OpenClash

```bash
cd /tmp
wget https://github.com/zerolabnet/OpenClash/releases/download/v0.45.16-beta/luci-app-openclash_0.45.16-beta_all.ipk
opkg install luci-app-openclash_0.45.16-beta_all.ipk
```
