# interesting files

arbitrary file read / file include / directory traval     check list

if you can read file

LFI or arbitrary file download

1. &#x20; resource try hacktricks -----   payloads all the thing

2\.  info gather

```
check directory listing    "."     "/"
/etc/issue
/etc/shadow
/etc/hostname
/etc/resolf.conf
capture smb
check file size format limit
defaul config files with service running on the target
history
/proc/self/environ

PHP
apache sessions directory

.NET
web.config --- key --- deserialize

Java
WEB-INF/web.xml
xxx.jar
middle ware config file  xxx.xml    xxx.properties

other
C:\Users\Username\.aws\credentials    /.aws/credentials
.config/.......         kubernetes

.env config
```

here is some file to try

```
apache config file

/etc/apache2/sites-enabled/000-default.conf    or other may webdav or other info
/etc/passwd

/etc/iptables/rules.v4              //firewall
/etc/iptables/rules.v46

不要过于依赖具有列目录的文件读取漏洞，有些列目录的漏洞无法操控，可能不显示隐藏文件，但还是可读的要考虑当前是什么文件夹有什么有趣的东西
.ssh

Another way to achieve RCE is through PHP session files. These files are usually store/var/lib/php/sessions/sess_<PHPSESSID>


```





