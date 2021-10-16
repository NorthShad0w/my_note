# 文件系统ADS

### Alternate Data Stream (ADS)



```bash
dir /R

powershell -command "get-item <file> -stream *"
powershell -command "get-item hm.txt -stream *"
powershell -command "get-content <file> -stream root.txt"
powershell -command "get-content hm.txt -stream root.txt"
```
