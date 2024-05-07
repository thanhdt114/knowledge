# Config Reverse Proxy

1. Open default config file
```bash
sudo gedit /etc/nginx/sites-available/default
```

2. Add content and click save button
```
server {
    listen 80;

    server_name 0.0.0.0;

    location /test/ {
        proxy_pass http://0.0.0.0:5500/;
    }


    # Add more location blocks for additional services as needed
}
```
