# net

打开被禁用的用户，（UID为500却无法psexec时有可能是这个问题在）

net user administrator /active:yes

UID不为500想psexec要关闭UAC

更改共享权限

net share Docs=D: /grant:everyone,FULL
