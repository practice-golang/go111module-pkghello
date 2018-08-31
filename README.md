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
* Because last release is v3.1.0 thus, you will never see the output - "Hello, this is 3.2.0", from this module. :-p
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
