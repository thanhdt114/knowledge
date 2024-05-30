# Install docker-compose
***NOTE***
Reference documents: [Install Compose standalone](https://docs.docker.com/compose/install/standalone/)

## Ubuntu
1. Download docker-compose
```bash
sudo curl -SL https://github.com/docker/compose/releases/download/v2.27.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
```
2. Grant docker-compose permissions
```bash
sudo chmod +x /usr/local/bin/docker-compose
```
3. Create a link to use docker-compose commands on the terminal
```bash
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```
4. Check docker-compose is installed successfully
```bash
docker-compose --version
```
- Output that you should get
```bash
Docker Compose version v2.27.0
```
