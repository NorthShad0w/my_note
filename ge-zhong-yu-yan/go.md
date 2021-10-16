# go

workspace $GOPATH

official proxy

```
export GO111MODULE=on
export GOPROXY=https://goproxy.io
GO111MODULE=on GOPROXY=https://goproxy.io
```

third party package

**logrus is better than official Go log package **`github.com/sirupsen/logrus`

**web router **`github.com/gorilla/mux`

web socket `github.com/gorilla/websocket`

web middle ware `github.com/urfave/negroni`   for example  process authentication

dns `github.com/miekg/dns`



```
go get -u github.com/google/go-cmp/cmp

import "github.com/google/go-cmp/cmp"

go get 

go dep

go mod

go fmt *.go automately format your source code

golint reports style mistakes

go vet inspect legitimate bugs


```



* Defers will be executed when a program panics, but calling `os.Exit(log.Fatal)` exits immediately, and deferred functions can't be run.
