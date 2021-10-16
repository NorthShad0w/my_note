# 主机发现

ip neigh

arp 缓存  arp -n

THC(the hacker's choice)   ----alive6 用来发现ipv6的

```
for /L %I in (1,1,254) DO @ping -w 1 -n 1 192.168.0.%I |findstr "TTL="


```

