# Config SSL By Let’s Encrypt

1. Install Certbot
- Run this command on the command line on the machine to install Certbot.
```bash
sudo snap install --classic certbot
```
or
```bash
sudo apt install certbot
```

2. Prepare the Certbot command
- Execute the following instruction on the command line on the machine to ensure that the `certbot` command can be run.
```bash
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```

3. Create SSL/TLS certificate
```bash
certbot certonly --standalone -d [domain_name] --staple-ocsp -m [email] --agree-tos
```

4. Add certificate to domain configuration in nginx
```bash
server {
    listen 443 ssl;
    # RSA certificate
    ssl_certificate [path]/fullchain.pem
    ssl_certificate_key [path]/privkey.pem
    include /etc/letsencrypt/options-ssl-nginx.conf;
}
```

## References
1. [Certbot instructions](https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal&tab=standard)
2. [Hướng dẫn tạo SSL/TLS](https://quoc9x.com/2023/04/20/huong-dan-tao-ssl-tls-mien-phi-voi-openssl-va-lets-encrypt/)
