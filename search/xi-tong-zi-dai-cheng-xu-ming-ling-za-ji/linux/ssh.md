# ssh

加算法

```
-oKexAlgorithms=+diffie-hellman-group1-sha1
```

转发 -R -L port:ip:port 即可

\-t bash     escape from ristricted shell      rbash

if return Permission denied (publickey)

try to force password authenticate

```
-o PreferredAuthentications=password -o PubkeyAuthentication=no
```

login with no pty no log

```
ssh -T user@host /bin/bash -i
```

\-T 代表不要分配 tty，-i 代表要一个交互型的 bash
