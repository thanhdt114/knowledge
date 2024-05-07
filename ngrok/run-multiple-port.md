# Run multiple port

1. Find the path to the config file
```bash
ngrok config check
```

2. Open config file
```bash
sudo gedit [path]
```

3. Add content like this:
```yml
tunnels:
  first:
    addr: 22
    proto: tcp    
  second:
    addr: 5500
    proto: http
  thirdth:
    addr: 6000
    proto: http
```

4. Run ngrok
```bash
ngrok start --all
```
