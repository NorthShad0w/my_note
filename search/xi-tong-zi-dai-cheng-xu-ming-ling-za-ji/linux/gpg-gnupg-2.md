# gpg / GnuPG 2

GnuPG uses a somewhat more sophisticated scheme in which a user has a primary keypair and then zero or more additional subordinate keypairs.

```
gpg --full-gen-key



$ gpg --list-keys
$ gpg --list-sigs   # list signatures
$ gpg --fingerprint # list fingerprints



Backup a private key:

$ gpg --export-secret-keys --output private-key.asc --armor <key-id>

$ gpg --allow-secret-key-import --import private-key.asc
```



### Export and import public keys

Export a public key to a 7-bit ASCII file:

```
$ gpg --armor --output my-public.key --export <key-id>
```

If no `<key-id>` has been entered, all present keys will be exported.

The public key can be freely distributed by sending it to friends, publishing on websites or registering it with public [key servers](https://github.com/bfrg/gpg-guide#key-servers).

In order to encrypt a documents for another user as well as to verify their signatures, we need their public key.

Import someone else's public key:

```
$ gpg --import some-public.key
```



### Encrypting and decrypting

After a public key has been imported, we can encrypt a file or message to that recipient:

```
$ gpg [--output <outfile>] --recipient <key-id> --encrypt <some-file>
```

By default the encrypted file will be appended a `.gpg` suffix. This can be changed with the `--output <outfile>` option.

To encrypt a file for personal use, `<key-id>` is simply the name or email address (or anything else) that was used during key generation.

When encrypting or decrypting a document, it is possible to have more than one private key in use. In this case, we need to select the active key with the option `--local-user <key-id>`. Otherwise the default key is used.

Decrypt a file that has been encrypted with our own public key:

```
$ gpg --output somefile.txt --decrypt somefile.txt.gpg
```

`gpg` will prompt for the passphrase and then decrypt and write the data to the file specified with the `--output` option.

Further options:

* `--armor, -a`: encrypt file using ASCII text
* `--hidden-recipient <user-id>, -R <user-id>`: put recipient key IDs in the encrypted message to hide receivers of message against traffic analysis
* `--no-emit-version`: avoid printing version number in ASCII armored output

### Signing and checking signatures

To avoid the risk that someone else claims to be you, it is useful to sign every document that is encrypted. If the encrypted document is modified in any way, a verification of the signature will fail.

Sign a file with your own key:

```
$ gpg --sign <file> --output <file.sig>
```

Note that the file is compressed before being signed. The output will be in binary format and thus won't be _human-readable_. To make a clear text signature, run:

```
$ gpg --clearsign <file> --output <file.sig>
```

This causes the document to be wrapped in an ASCII-armored signature but otherwise does not modify the document. Hence, the content in a clear text signature is readable without any special software. **OpenPGP** software is only required to verify the signature.

A disadvantage of above methods is that users who received the signed documents must edit the files to recover the original (since signature is now part of document). It is also possible to make a detached signature to a file:

```
$ gpg --armor --output <file.sig> --detach-sign <file>
```

This is highly recommended when signing binary files (like tar archives).

Sign and encrypt a file:

```
$ gpg --sign <file> [--armor] --encrypt --recipient <user-id> [--local-user <key-id>]
```

`--local-user <key-id>` specifies the key to sign with, it overrides `--default-key <key-id>` option, which is usually specified in `~/.gnupg/gpg.conf`.

When an encrypted file has been signed, the signature is usually checked when the file is decrypted using the `--decrypt` option:

```
$ gpg --output <file> --decrypt <file.gpg>
```

To just check the signature use the `--verify` option:

```
$ gpg --verify <pgp-file/sig-file>
```

This assumes the signer's public key has already been imported.

Assuming we downloaded a file `archive.tar.gz` and a corresponding detached signature `archive.tar.gz.asc`, we can verify the signature after downloading the signer's public key as follows:

```
$ gpg --verify archive.tar.gz.asc archive.tar.gz
```
