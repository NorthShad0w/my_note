# rustscan

内网精细化端口判活还是建议制定来源端口过防火墙减小误差

扫描量非常大，如果要隐蔽的话可以用-b参数

端口判活

```
sudo docker run -it --rm --name rustscan rustscan/rustscan:latest
alias rustscan='sudo docker run -it --rm --name rustscan rustscan/rustscan:latest'

docker version is not stable
compile from the source

rustscan -g -a 127.0.0.1 --scan-order Random -b 60000
```
