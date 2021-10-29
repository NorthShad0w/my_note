# pwntools

set context

```
context.arch = 'i386'
context.os = 'linux'
context.endian = 'little'
context.log_level = 'INFO'
```

functions

```
exp_sender = remote(remote_server, remote_port)

exp_sender.sendlineafter("OK Ready. Send USER command.\n","DEBUG")
exp_sender.recvuntil("OK Ready. Send USER command.")

p32(0x123123)
p64(0x123123)

exp_sender.interactive()
```
