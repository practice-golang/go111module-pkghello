# Practice for GO111MODULE

## Init & Build
```bash
go mod init
go build
```

## Modify & Build
```bash
go mod tidy
go build
```

## Example using this module
```go
// go111module-apphello
package main
 
import (
    hell "github.com/practice-golang/go111module-pkghello/v3"
)
 
func main() {
    hell.Hello()
}
```
