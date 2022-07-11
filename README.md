# go-log

The golog library provides a fast and simple logger dedicated to JSON output.

golog's library is a wrapper of [Zerolog](https://pkg.go.dev/github.com/rs/zerolog#) to desacople the solutions with the Zerolog API 

## How to build?

this is a library, we are not going to build it.

## How to test?

there are two options to test this library.

1. running go tool

```sh
go test -race ./...
```

2. running make

```sh
make test
```

## How to use?

1. You can add this library to your application as explained below.

```sh
go get github.com/akatsuki-members/credit-crypto/libs/go-log
```

2. Simple logging example

```
package main

import (
    "github.com/akatsuki-members/credit-crypto/libs/go-log"
)

func main() {
    log.Info("hello world")
}

// Output: {"time":1516134303,"level":"debug","message":"hello world"}
```

* You only need to provide a router that implements this function.

```go
func(http.ResponseWriter, *http.Request)
```

* You can add one common endpoint or all of them.

```go
import "github.com/akatsuki-members/credit-crypto/libs/common-endpoints/internal/handlers/heartbeat"
...
mux := http.NewServeMux()
...
endpoints.New(mux).WithHeartbeat().WithHealth().WithInfo()
```
