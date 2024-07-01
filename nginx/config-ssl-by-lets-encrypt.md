# Config SSL By Let’s Encrypt

## Install certbot follow
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
