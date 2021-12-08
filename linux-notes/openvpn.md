# openvpn

最终成功安装是按ubuntu上的教学走的

要想利用vpn上网的话

防火墙要关，server的设置里，打开转发，打开dns

最关键的，要利用iptables的nat表

```
sudo iptables -t nat -A POSTROUTING -s 10.8.0.0/24 -o eth0 -j MASQUERADE
sudo iptables-save   (ubuntu)
sudo service iptables save   (redhat)
sudo systemctl restart iptables (redhat)
```
