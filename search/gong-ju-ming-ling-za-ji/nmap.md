# nmap

快速扫描提取端口(没必要，慢且不准，建议使用rustscan或者masscan)

真实情况倒是可以慢一点

```
ports=$(sudo nmap -p- --min-rate=1000 -T4 10.129.1.35 | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//)
--source-port 53
```

nmap还是建议确定开放端口后做进一步分析
