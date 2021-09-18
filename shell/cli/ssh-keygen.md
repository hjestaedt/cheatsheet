# ssh-keygen

###### __create new keypair__
`ssh-keygen -t rsa -b 4096 -C "email@example.com`  
`ssh-keygen -t ecdsa -b 521 -C "email@example.com"`

###### __generate public-key from private key__
`ssh-keygen -y -f private-key`

###### __add/change passphrase__
`ssh-keygen -p -f private-key`

###### __add/change comment__
`ssh-keygen -c -C "new comment" -f private-key`

###### __copy public key to remote host (~/.ssh/authorized_keys)__
`ssh-copy-id -i private-key user@host`
