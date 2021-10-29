# setuid\_trick.c

```c
#include <stdio.h>
#include <unistd.h>

int main(int argc, const char * argv[]){
    printf("%2",  execvp(argv[1], &argv[1]));
    return 0;
}
```
