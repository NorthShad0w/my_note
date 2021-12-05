# openssl

```
req: initiate a new certificate signing request
-newkey: generate a new private key
rsa:2048: use RSA encryption with a 2,048-bit key length. 
-nodes: store the private key without passphrase protection 
-keyout: save the key to a file 
-x509: output a self-signed certificate instead of a certificate request
-days: set validity period in days
-out: save the certificate to a file 
```

#### Key Generation

```
private key
openssl genpkey -out fd.key -algorithm RSA

public key
openssl pkey -in test.key -pubout
```

