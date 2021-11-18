# sqlmap

```
eval 参数
sqlmap -u "http://xxxxxx.com/?id=" --eval "import base64; p=base64.b64encode('{\"a\":\"%s\",\"b\":\"2\",\"c\":\"3\"}'%p)"

sqlmap api  可以和msf 或者burp联合，都需要插件，还没试过

mysql windows 弱密码可以直接用这里自带的脚本，还是比较好用的
自带的命令执行可能会用缓存问题，回显不一定可信，加组成功net user 不一定回显，直接加，自信登录就可以了
```

