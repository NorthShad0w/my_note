# 一些 典型ssrf 技巧

#### SSRF via Request Splitting <a href="the-vulnerability-ssrf-via-request-splitting" id="the-vulnerability-ssrf-via-request-splitting"></a>

nodejs <= version 8

new\_line = '\u010D\u010A'&#x20;

space = '\u0120'



http.server

serve index.html

wget 10.10.17.114  is ok&#x20;

don't need 10.10.17.114/evil.file     **/evil.file**

****

**direct admin.xx.com   blacklisted**

try redirect       \<your ips>/index.php   ---->302         admin.xx.com   &#x20;



ssrf port scan   try 127.0.0.1 localhost hex ......

domain name resolve to 127.0.0.1



dns rebinding

{% embed url="https://lock.cmpxchg8b.com/rebinder.html" %}

A good reminder to try both of them just in case when fuzzing things.



sometimes `../` worked     hackthebox  Unicode  &#x20;

```
http://hackmedia.htb/static/   is   white list
```

```
http://hackmedia.htb/static/../redirect/?url=10.10.17.95/jwks.json 
```

I have no idea why this could work



construct gopher

proxy to burp  content-lenth add 2     url-encode-all



