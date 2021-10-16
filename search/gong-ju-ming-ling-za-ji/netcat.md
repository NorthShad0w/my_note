# netcat/ncat

内网中可以用作端口扫描工具来用

nc -vz 192.168.122.4 1-65535 2>&1 | grep succeed

若是下列情况，192.168.5.2存在错误配置防火墙，放行了53源端口流量，987开放ssh监听，指定源端口过防火墙。

ncat -l 4444 --sh-exec "ncat 192.168.5.2 987 -p 53" &

windows的反弹shell可以用rlwrap包装监听



**ncat -k**  allow multiple connections
