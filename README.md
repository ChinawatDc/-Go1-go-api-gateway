# Go API Gateway

## Project Setup

### 1. Install Go

Make sure you have Go installed. If not, download and install it from: Go Downloads

### 2. Create a Project Directory

```sh
mkdir go-api-gateway
cd go-api-gateway
```

### 3. Initialize Go Module

```sh
go mod init go-api-gateway
```

### 4. Install Dependencies

```sh
go get -u github.com/gin-gonic/gin
```

### 5. Create `main.go`

Create a file named `main.go` and add the following code:

```go
package main

import (
	"net/http"

	"github.com/gin-gonic/gin"
)

func main() {
	r := gin.Default()

	// Health check route
	r.GET("/api/v1/health", func(c *gin.Context) {
		c.JSON(http.StatusOK, gin.H{
			"status":  "healthy",
			"message": "API Gateway is running",
		})
	})

	r.Run(":8080") // Start server on port 8080
}
```

### 6. Run the Project

```sh
go run main.go
```

### 7. Test the API

You can test the API using `curl` or Postman:

```sh
curl http://localhost:8080/api/v1/health
```

#### Expected Response:

```json
{
  "status": "healthy",
  "message": "API Gateway is running"
}
```

## Additional Notes

- This API Gateway is built using `gin-gonic/gin`.
- You can extend it by adding authentication, logging, or proxying requests to other services.
- To stop the server, press `CTRL+C`.
# -Go1-go-api-gateway
