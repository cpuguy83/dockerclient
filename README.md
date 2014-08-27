# Dockerclient

Dockerlient is a client library for Docker written in go, with a straight-forward
syntax.

### Usage

```go
package main

import(
  docker "github.com/cpuguy83/dockerclient"
  "fmt"
)

func main() {
  client := docker.NewClient("tcp://127.0.0.1:2375")

  containers, err := client.FetchAllContainers()
  if err != nil {
    return err
  }

  for _, container := range containers {
    fmt.Println(container.Name)
  }
}
```
