# openssl cheetsheet

## sample openssl config
```
[req]
distinguished_name = req_distinguished_name
req_extensions = v3_req
prompt = no
[req_distinguished_name]
C = YOUR_COUNTRY
ST = YOUR_STATE
L = YOUR_CITY
O = YOUR_ORG
OU = YOUR_ORG_UNIT
CN = YOUR_DOMAIN
[v3_req]
subjectAltName = @alt_names
[alt_names]
DNS.1 = ADDITIONAL_DOMAINS
```

## create selfsigned certificate
```
openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365 -config req.conf
```

## create csr 
```
openssl req -new -out san_domain_com.csr -key key.pem -config req.conf
```

## create selfsigned certificate with alternative domain names
```
openssl genrsa -out private.key 2048
openssl req -new -out private.csr -key private.key -config req.conf
openssl req -text -noout -in private.csr
openssl x509 -req -days 365 -in private.csr -signkey private.key -out private.crt -extensions v3_req -extfile YOUR_CONFIG_FILE

openssl rsa -in private.key -text
openssl x509 -in private.crt -text
```

For windows machines you can use _winpty_ in case the command is not executing properly.