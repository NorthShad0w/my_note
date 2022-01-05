# 反射调用

powershell 利用.net 反射调用任意dll 程序集里的任意函数

```powershell
# 适用于 Windows 10 1803 之后版本的windows
function LookupFunctions {
    Param ($moduleName, $functionName)
    
    # 获取system.dll 的地址 在这里面 反射找到 getmoduleHandle 和 getProcAddress
    $assem = ([AppDomain]::CurrentDomain.GetAssemblies() | Where-Object { $_.GlobalAssemblyCache -And $_.Location.Split('\\')[-1].Equals('System.dll') }).GetType('Microsoft.Win32.UnsafeNativeMethods')
    
    $GetModuleHandle = $assem.GetMethod('GetModuleHandle')
    $targetdll = $GetModuleHandle.Invoke($null, @($moduleName))
    $tmp=@()
    $assem.GetMethods() | ForEach-Object {If($_.Name -eq "GetProcAddress") {$tmp+=$_}}
    return $tmp[0].Invoke($null, @($targetdll, $functionName))
}

$virtualalloc = LookupFunctions kernel32.dll VirtualAlloc
```
