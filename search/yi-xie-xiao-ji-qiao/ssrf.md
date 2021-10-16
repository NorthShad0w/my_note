# 一些 典型ssrf 技巧

#### SSRF via Request Splitting <a href="the-vulnerability-ssrf-via-request-splitting" id="the-vulnerability-ssrf-via-request-splitting"></a>

nodejs <= version 8

new_line = '\u010D\u010A' 

space = '\u0120'



http.server

serve index.html

wget 10.10.17.114  is ok 

don't need 10.10.17.114/evil.file     **/evil.file**

****

**direct admin.xx.com   blacklisted**

try redirect       \<your ips>/index.php   ---->302         admin.xx.com    



ssrf port scan   try 127.0.0.1 localhost ......

A good reminder to try both of them just in case when fuzzing things.



construct gopher

proxy to burp  content-lenth add 2     url-encode-all
