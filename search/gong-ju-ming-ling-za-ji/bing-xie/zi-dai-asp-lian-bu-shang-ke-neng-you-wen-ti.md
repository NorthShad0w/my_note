# 自带asp连不上可能有问题

在一台2003 iis6.0上发现的

可能还要给用户对于当前目录的everyone权限

在开始加一句

<%@LANGUAGE="VBSCRIPT" CODEPAGE="65001"%>

具体是什么用还没有研究

注：当时整站是不是UTF-8编码的，是GBK，所以强行指定CODEPAGE为65001，应该是可以用UTF-8编码来交流，这样可以避免报错吧？大概。
