# pwn

file 查看文件类型，得到基本的信息

checksec

动态调试 gdb+gef

ldd - print shared object dependencies        本地找libc地址用

readelf - \[display infomation about ELF files]  + grep   本地找某个libc的某个函数

strings -a -t x /lib32/libc.so.6 | grep /bin/sh 找libc的/bin/sh

如果没有strings 和 readelf的话 如果想要在目标机器上找，可以试试gdb 原版

strace - trace system calls and signals

r2 --------radare2 - Advanced commandline hexadecimal editor, disassembler and debugger
