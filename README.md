Ubuntu 16.04 | Debian 8.x

```
# 可选：apt -y install libevent-dev libnet1-dev libssl-dev libpcap-dev

###### 0.Dependence/Dependence.md
```

1.解密机器配置
```
> openssl genrsa -out ca.key 4096
> openssl req -new -x509 -days 1826 -key ca.key -out ca.crt

> echo 1 > /proc/sys/net/ipv4/ip_forward

> iptables -I INPUT -j ACCEPT
> iptables -I FORWARD -j ACCEPT

> iptables -t nat -I PREROUTING -p tcp --dport 443 -j REDIRECT --to-ports 8443

> sslsplit -D -k ca.key -c ca.crt -l connect.log -L sample.log https 0.0.0.0 8443

###### 可选：转发到IDS机器
> sslsplit -D -k ca.key -c ca.crt -l connect.log -L sample.log https 0.0.0.0 8443
-T 192.168.8.3 -I eth0
```

2.内网主机配置
```
> ip route change default via 192.168.8.2 dev ens192

##### 修改程序行为，默认加上参数，举例：curl

1.vi curl.sh 
#!/bin/sh

curl='/usr/bin/curl-bak -k'
exec $curl $@

2.
cp /usr/bin/curl /usr/bin/curl-bak
cp curl.sh /usr/bin/curl
chmod +x /usr/bin/curl

3.测试
curl https://z.cn
```

#############################

```
备注：
1.浏览器HTTPS流量解密可以使用Wireshark + SSLKEYLOGFILE 
2.Burp Suit  根证书 或 透明代理（未测试）
3.如程序不支持“不安全”的SSL连接和传输，需要把自签名的根证书添加到系统
```
