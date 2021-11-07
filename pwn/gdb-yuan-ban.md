# gdb

```
info b               # show breakpoints
del  2               # delete breakpoint 2
break 6              # set breakpoint at file demo.c line 6
break *0x4334343      # set break point
si                    # step in
fini                  # finish a function
r                    run
c                    continue

```

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

By default, when a program forks, GDB will continue to debug the parent process and the child process will run unimpeded.

If you want to follow the child process instead of the parent process, use the command `set follow-fork-mode`.

and&#x20;

```
set detach-on-fork off

info inferiors
inferiors 2
```

useful debugging programs whose parent process listening on a port and fork a child process to handle incoming connections

### read some string

```
x/s $rdi
```





