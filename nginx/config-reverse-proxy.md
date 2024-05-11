# Config Reverse Proxy

**NOTE**
Should create each file for 1 domain for easy management

1. Create config file
```bash
sudo gedit /etc/nginx/conf.d/domain.conf
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
	server_name domain.local;
	location / {
		proxy_pass http://IP:8080;
	}
}

```
3. Restart nginx
```bash
sudo service nginx restart
```
