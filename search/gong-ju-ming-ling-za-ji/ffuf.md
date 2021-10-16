# ffuf

稍微记录一些常用的

```
---!!!---Have to Change the Default User-Agent Header---!!!---

目录fuzz
-u                目标url
-w                字典可以用逗号分割
-recursion        递归 recursion-depth 深度
-e                扩展名

ffuf -u https://W2/W1 -w ./wordlist.txt:W1,./domains.txt:W2   多位置fuzz
clusterbomb mode (default)  顺序先用尽第一个然后第二个加一 大量扫描防止被ban


处理授权问题
-b               cookie 
-H                客制化head头

其他
-c                加颜色，加了颜色之后，pipe可能会不方便
-s                silent 方便pipe 和rustscan的-g同理
-ac                自动校准过滤，跟据长度
-acc                客制化自动校准过滤

-sa，-se，-sf        不同程度的自动停止

-p                延迟  可以设置成2（两秒）或者0.1-2.0（在这两者之间随机）
-rate                限制每秒发包

-mc                匹配返回码
-mr                正则匹配返回包，比较好用

-fc                过滤匹配，有各种的

-replay-proxy        把成功匹配（排除过滤匹配）的请求包往代理重放一次（这些包一共访问了两次）
-x                proxy

-mode             多字典转换成pitchfork

-request            使用抓的包

subdomain      no DNS
ffuf -c -w /usr/share/ -u http://schooled.htb -H "Host: FUZZ.schooled.htb" -fw 5338
```

