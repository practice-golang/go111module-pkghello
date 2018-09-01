# Practice for GO111MODULE

## Init & Build
```bash
go mod init
go build
```

## Change module & Build
```bash
go mod tidy
go build
```

## Example using this module
* Because last release is v3.1.0 thus, you will never see the output - "Hello, this is 3.2.0", from this module. :-p
* [Because of this rule](https://github.com/golang/go/wiki/Modules#semantic-import-versioning), v0 and v1 will not work.
* Current github.com/practice-golang/go111module-pkghello point to v3.2.0 but go mod try to find v1.0.0 so, this base path will not work too.
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
