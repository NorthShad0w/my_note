# find

find 目录 可以递归查看该目录下所有文件，很方便

suid

```
find / -perm -u=s -type f 2>/dev/null
```

writable

```
find . -writable -ls
```
