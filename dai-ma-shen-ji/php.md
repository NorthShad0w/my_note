# php

打开报错功能

常见审计点

反序列化

type juggling

```php
echo intval('asd');    # 0
var_dump(0 == 'asd');   # true
var_dump('asd' == 0);   # true
var_dump('0x1999' == 0); % tr
```

如果有文件可以控制而且可读取的话，可以用phar反序列化
