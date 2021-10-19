# 1. intro & install

The radare development repository is often more stable than the 'stable' releases.

The most important one is `sys/install.sh`. It will pull, clean, build and symstall r2 system wide.

Symstalling is the process of installing all the programs, libraries, documentation and data files using symlinks instead of copying the files.

In addition, r2 has an embedded webserver and ships some basic user interfaces written in html/js. You can start them like this:

```
$ r2 -c=H /bin/ls
```

GUI&#x20;

Xarkes decided to fork it under the name of Cutter

{% embed url="https://github.com/radareorg/cutter" %}
