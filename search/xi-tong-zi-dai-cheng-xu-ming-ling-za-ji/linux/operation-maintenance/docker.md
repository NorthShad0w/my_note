---
description: 单纯收集一些常用的命令，主要还是翻manual
---

# docker

`Docker images are read-only templates used to build containers.`

sudo docker pull    拉取镜像

sudo docker run    运行镜像：

run 是 create 和 start 的联合 如果没加--rm container不会被删除

```
-a     Attach
-d     Detach        run in background
-i      Keep STDIN open even if not attached
-t      Allocate a pseudo-TTY
--rm    Automatically remove the container when it exits
--name <string>  Assign a name to the container
-e     设置环境变量

examples:
比如我要用docker进行rustscan
sudo docker run -it --rm --name rustscan rustscan/rustscan:latest
想方便点就在 .zshrc里面加
alias rustscan='sudo docker run -it --rm --name rustscan rustscan/rustscan:latest'

设置环境变量example
docker run --name mysql-1 -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password -d mysql
```



如果拉取了mongodb mysql postgresql 之类的数据库镜像   这些镜像里面自带命令行管理工具，可以不用在宿主机上安装管理工具



```
mongodb 一次性shell
sudo docker run -it --link=[mongo-container-name]:mongo --rm mongo sh -c 'exec mongo "$MONGO_PORT_27017_TCP_ADDR:$MONGO_PORT_27017_TCP_PORT/store"'

mysql 一次性shell
sudo docker run -it 


```
