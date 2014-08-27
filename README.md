# Dockerclient

Dockerlient is a client library for Docker written in go, with a straight-forward
syntax.

### Usage

```go
package main

import(
  docker "github.com/cpuguy83/dockerclient"
  "fmt"
  "os"
)

func main() {
  client := docker.NewClient("tcp://127.0.0.1:2375")

  containers, err := client.FetchAllContainers()
  if err != nil {
    fmt.Println(err)
    os.Exit(1)
  }

  for _, container := range containers {
    fmt.Println(container.Name)
  }
}
```
