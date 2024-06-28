# Config SSL

1. Create private key
```bash
sudo openssl genrsa -out wisdom.private.key 2048
```

2. Create csr file
```bash
sudo openssl req -key wisdom.private.key -new -out wisdom.csr
```
Enter the requested information\
"Common Name" information: enter your domain name

