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
* [Because of this rule](https://github.com/golang/go/wiki/Modules#semantic-import-versioning), v0 and v1 will not work. You can use only v2 or v3
* Current [master branch](https://github.com/practice-golang/go111module-pkghello) point to v3.2.0 but go mod will try to find v1.0.0 so, [base path](https://github.com/practice-golang/go111module-pkghello) will not work too.
    * When upgrade your package managing from `/V0` (or `/v1`) to `/Vn`, you should create and use a new branch instead of `master`.
    * E.g. `v0`, `v1` can be used at the `master` branch, others like `/v2` are should be used at `/v2`
* If location of below Go source file is $GOPATH/src/{package name}, import comment is not needed.
```go
package main // import "github.com/practice-golang/pkghello"

import (
    hell "github.com/practice-golang/go111module-pkghello/v3"
)

func main() {
    hell.Hello()
}
```
