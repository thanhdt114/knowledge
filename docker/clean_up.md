# Clean Up

1. View total storage
```bash
docker system df
```

2. Delete unused images ***(delete all images not being used by any container)***
```bash
docker image prune -f
```

3. Delete unused volumes ***(delete all volumes not being used by any container)***
```bash
docker volume prune -f
```

4. Delete unused build cache ***(delete all builders not being used by any container)***
```bash
docker builder prune -f
```
