# proxychains

proxychains -q -f



proxychains looks for config file in following order:

```
file listed in environment variable PROXYCHAINS_CONF_FILE or provided as a -f argument to proxychains script or binary.
./proxychains.conf

$(HOME)/.proxychains/proxychains.conf

/etc/proxychains.conf

/etc/proxychains4.conf

More information is provided in /etc/proxychains4.conf file.
```
