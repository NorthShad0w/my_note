# python

smtpd

```
# old, deprecated, but install default
sudo python3 -m smtpd -n -c DebuggingServer 0.0.0.0:25
# new
sudo python3 -m aiosmtpd -l 0.0.0.0:25 -d
```

命令执行回显

```
return subprocess.check_output, (['cat', 'flag_wIp1b'],)
```

venv module

```
sudo apt install python3-venv
python3 -m venv <file_name_you_like>
source <file_name_you_like>/bin/activate
deactivate
```



