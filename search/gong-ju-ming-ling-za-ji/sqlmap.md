# sqlmap

```
eval 参数
sqlmap -u "http://xxxxxx.com/?id=" --eval "import base64; p=base64.b64encode('{\"a\":\"%s\",\"b\":\"2\",\"c\":\"3\"}'%p)"

sqlmap api  可以和msf 或者burp联合，都需要插件，还没试过
```

