# linux 痕迹擦除

命令前加空格不会被记录

```
[空格]set +o history     设置不记录
set -o history         恢复
history -d [num]      删除
history -c
```
