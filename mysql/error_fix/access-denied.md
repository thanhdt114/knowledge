# Access denied

***NOTE***
Access mysql as root user and perform the following steps

1. Drop existing user
```bash
DROP USER '[username]'@'[host]';
```

2. Create user
```bash
CREATE USER '[username]'@'%' IDENTIFIED BY '[password]';
```

3. Add grant
```bash
GRANT ALL PRIVILEGES ON *.* TO '[username]'@'%';
````

4. Update grant
```bash
FLUSH PRIVILEGES;
```
