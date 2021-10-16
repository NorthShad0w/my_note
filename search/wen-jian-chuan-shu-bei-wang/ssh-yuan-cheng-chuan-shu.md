# ssh_remote_transfer

scp

rsync



文件挂载

```
sudo sshfs -o allow_other,default_permissions user@machine:/path/to/program /mnt/debug
```

If you run into an issue where you can't write to files in the the remote mounted directory, try removing the 'default_permissions' flag when running SSHFS:
