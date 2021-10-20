# linux

### linpeas

### pspy

mounting [/proc with hidepid=2](https://linux-audit.com/linux-system-hardening-adding-hidepid-to-proc/). I can see this by running `mount`:

guly@unattended:/boot$ mount | grep ^proc&#x20;

proc on /proc type proc (rw,relatime,hidepid=2)

this can harden the linux machine which makes the pspy useless

### check groups&#x20;

if user has a group id that does not belongs to [https://wiki.debian.org/SystemGroups](https://wiki.debian.org/SystemGroups) may lead to priv\_esc

example check: (grub group)

`find / -group grub 2>/dev/null`

