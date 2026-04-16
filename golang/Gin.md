
# Import
```go
import ("github.com/gin-gonic/gin")
```
# Init
```go
r := gin.Default()
r.Run(":8080")
```
# Group
```go
v1 := r.Group("/api/v1")
```
