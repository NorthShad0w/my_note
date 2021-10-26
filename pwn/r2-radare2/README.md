# r2 - radare2

radare2 - Advanced commandline hexadecimal editor, disassembler and debugger

usage:

r2 \[file]

```
command:
aaa ------------------   code analyze a or aa 
afl ------------------   function list
vvv ------------------   visualization  panel mode
pdf@main ----------------    print disassember function 
? 0x149a -----------------    display 0x149a in another numeric base.
pdc @ main -----------------  display pseudo c code 
i?   ----------------------   get binary info  

## The pdc command is unreliable especially in processing loops (while, for, etc.). 
## So I prefer to use the r2dec https://github.com/wargio/r2dec-js

s 0x804856c ------------  seek
ps   -------------------   print string




```
