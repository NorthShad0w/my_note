# masscan

```
全端口扫描
sudo masscan -p1-65535,U:1-65535 10.10.10.109 --rate=10000 -e tun0 | tee ports
提取开放端口
ports=$(cat ports | awk -F " " '{print $4}' | awk -F "/" '{print $1}' | sort -n | tr '\n' ',' | sed 's/,$//')
```

masscan have some problem scan udp

if target machine have a firewall

it can't  show   open| filter  item in traditional nmap UDP scan

for example   tftp  UDP  69

