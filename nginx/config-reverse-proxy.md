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
	location / {
	    add_header Content-Type text/plain;
	    return 200 'Welcome';
	}
}

server {
	listen 80;
	server_name domain1.local;
	location / {
		proxy_pass http://IP:8080;
	}
}

```
3. Restart nginx
```bash
sudo service nginx restart
```
