# wmic

把整个C盘添加进Windows Defender的白名单

```
wmic /Node:localhost /Namespace:\Root\Microsoft\Windows\Defender Path MSFT_MpPreference call Add ExclusionPath="C:\"
```

不知道怎么回事，在我的windows10上用不了
