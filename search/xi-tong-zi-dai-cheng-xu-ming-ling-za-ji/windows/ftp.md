# ftp



```bash
echo open 192.168.1.115 21> ftp.txt
echo 123>> ftp.txt 
echo 123>> ftp.txt 
echo binary >> ftp.txt 
echo get robots.txt >> ftp.txt
echo bye >> ftp.txt

ftp -s:ftp.txt
```
