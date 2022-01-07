# Hooking with Frida

Frida allows us to hook Win32 APIs through a Python backend while using JavaScript to display and interpret arguments and return values.

```
frida-trace -p 1584 -x amsi.dll -i Amsi*
```
