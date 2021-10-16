# cacls / icacls

```
display permission file or directory

icacls root.txt
cacls root.txt
```

更改文件权限

icacls root.txt /grant alfred:F

Cacls D: /t /e /c /g testuser:f

Cacls .\root.txt /t /e /c /g testuser:f

seems no difference

**powershell**

**Get-acl**

