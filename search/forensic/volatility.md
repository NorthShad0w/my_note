# volatility

volatility kdbgscan -f SILO-20180105-221806.dmp

volatility -f SILO-20180105-221806.dmp --profile Win2012R2x64 hivelist

```
0xffffc00000028000 0x0000000000a70000 \REGISTRY\MACHINE\SYSTEM
0xffffc00000619000 0x0000000026cc5000 \SystemRoot\System32\Config\SAM

volatility -f SILO-20180105-221806.dmp --profile Win2012R2x64 hashdump -y 0xffffc00000028000 -s 0xffffc00000619000
```
