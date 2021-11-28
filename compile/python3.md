# python3

#### code Hygiene

```
from import
import
def
class
if __name__ == '__main__'
```



//  full division

pow(x,y,z) X 的Y 次方 用Z 取模



编码后是字节，字节可以解码成字符串

b'\xe6\x88\x91\xe8\xbf\x98\xe7\x88\xb1\xe4\xbd\xa0' 我还爱你

b'\x73\x74\x72\x69\x6e\x67'          'string'

对于一些比较麻烦的要转移处理的字符串可以直接用字节流

for i in $(xxd -p test.object | sed 's/../\\\x&/g'); do echo "payload += b'$i'";done



Negative Indexes

Negative indexes start at the end of a string with -1

'hello'.find('e')              1  &#x20;







