# mount

The `mount` command also shows that most of the places I like to run scripts from are mounted with `noexec`:

```
guly@unattended:/boot$ mount | grep -e "tmp " -e shm
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,noexec)
tmpfs on /tmp type tmpfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /var/tmp type tmpfs (rw,nosuid,nodev,noexec,relatime)
```
