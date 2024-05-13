# Config Reverse Proxy

**NOTE**
Should create each file for 1 domain for easy management

**NOTE**
Change the values at [value_type] with actual values

1. Create config file
```bash
sudo gedit /etc/nginx/conf.d/[domain_name].conf
```

2. Add content and click save button

- Return text
```
server {
	listen 80;
	server_name 0.0.0.0;
	location / {
	    add_header Content-Type text/plain;
	    return 200 '[text]';
	}
}
```

- Forward order ip+port
```
server {
	listen 80;
	server_name [domain_name];
	location / {
		proxy_pass http://[ip]:[port];
	}
}

```
3. Restart nginx
```bash
sudo service nginx restart
```
