# ssh-keygen

###### __configuration for self-signed SAN cert__
```bash
[req]
default_bits = 4096
default_md = sha256
distinguished_name = req_distinguished_name
x509_extensions = v3_req
prompt = no
[req_distinguished_name]
C = DE
ST = Hessen
L = Foobar City
O = Foobar Inc
OU = Foobar Unit
CN = 192.168.1.100
[v3_req]
keyUsage = keyEncipherment, dataEncipherment
extendedKeyUsage = serverAuth
subjectAltName = @alt_names
[alt_names]
IP.1 = 192.168.1.100
```

###### __create certificate using a config file__
```bash
openssl req -new -nodes -x509 -days 730 -keyout mycert.key -out mycert.crt -config mycert.conf
```
