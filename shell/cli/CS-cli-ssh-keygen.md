---
tags: cheatsheet/shell/cli
---

# ssh-keygen

###### __create new keypair__
```bash
ssh-keygen -t rsa -b 4096 -C "comment"
ssh-keygen -t ecdsa -b 521 -C "comment"
ssh-keygen -t ed25519 -C "comment" 
```

###### __generate public-key from private key__
```bash
ssh-keygen -y -f private-key
```


###### __add/change passphrase__
```bash
ssh-keygen -p -f private-key
```

###### __add/change comment__
```bash
ssh-keygen -c -C "new comment" -f private-key
```

###### __copy public key to remote host (~/.ssh/authorized_keys)__
```bash
ssh-copy-id -i private-key user@host
```
