# 一些前置知识

### 两种syntax

assembly language has two syntaxes for source code

```
the instruction to add four to the EAX register
AT&T:
add $0x4,%eax

Intel:
add eax,0x4

```

The GNU Assembler (Gas) and many other GNU tools, including gcc and gdb, utilize AT\&T syntax.

Assemblers utilizing Intel syntax include the Microsoft Assembler (MASM), Borland’s Turbo Assembler (TASM), and the Netwide Assembler (NASM).
