# Golf

[![Build Status](https://drone.io/github.com/dinever/golf/status.png)](https://drone.io/github.com/dinever/golf/latest)

A web framework in Go.

Homepage: [golf.readthedocs.org](http://golf.readthedocs.org)

## Installation

    go get github.com/dinever/golf

## Hello World

```go
package main

import "github.com/dinever/golf"

func mainHandler(ctx *Golf.Context) {
  ctx.Write("Hello World!")
}

func pageHandler(ctx *Golf.Context) {
  page, err := ctx.Param("page")
  if err != nil {
    ctx.Abort(500)
    return
  }
  ctx.Write("Page: " + page)
}

func main() {
  app := Golf.New()
  app.Get("/", mainHandler)
  app.Get("/p/:page/", pageHandler)
  app.Run(":9000")
}
```

The website will be available at http://localhost:9000.

## Docs

[golfweb.github.io](http://golfweb.github.io).

## License

[MIT License](/LICENSE)
