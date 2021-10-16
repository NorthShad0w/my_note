# docker/ container

The commands below can confirm whether the current shell is situated within a docker container

```
grep -i docker /proc/self/cgroup 2>/dev/null
find / -name "*dockerenv*" -exec ls -la {} \; 2>/dev/null
```
