# gdb 原版

在 readelf 和 strings 没有的情况下找system exit 和 '/bin/sh'

```
先是用gdb运行目标程序
然后CTRL + C 中断目标程序
输入
p system
得到地址
p exit

find &system,+9999999, "sh"
```
