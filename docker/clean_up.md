# Clean Up

1. View total storage
```bash
docker system df
```

2. Delete unused images
```bash
docker image prune -f
```

3. Delete unused volumes
```bash
docker volume prune -f
```

4. Delete unused build cache
```bash
docker builder prune -f
```
