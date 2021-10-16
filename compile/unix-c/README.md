# C

[https://thoughtbot.com/blog/the-magic-behind-configure-make-make-install](https://thoughtbot.com/blog/the-magic-behind-configure-make-make-install) nice 



./configure

make

sudo make install





automake

[http://www.gnu.org/software/automake/manual/html_node/Introduction.html](http://www.gnu.org/software/automake/manual/html_node/Introduction.html)  1





m4 macro

configure.ac

```
AC_INIT([helloworld], [0.1], [george@thoughtbot.com])
AM_INIT_AUTOMAKE
AC_PROG_CC
AC_CONFIG_FILES([Makefile])
AC_OUTPUT
```



Makefile.am

```
AUTOMAKE_OPTIONS = foreign
bin_PROGRAMS = helloworld
helloworld_SOURCES = hello.c
```

aclocal

autoconf 

automake --add-missing    or automake -a

## [Distributing the program](https://thoughtbot.com/blog/the-magic-behind-configure-make-make-install#distributing-the-program)

./configure 

make dist  distribute

make distcheck      check the distribution tarball under a variety of conditions

##





