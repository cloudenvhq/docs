---
layout: default
title: CloudEnv Universal
parent: Installation
nav_order: 2
---

## CloudEnv Universal

Using CloudEnv's Universal sourcing is easy.

```console
$ eval $(cloudenv source) && path/to/start/command
```

Here is an example of a simple `hello.go` file you could use to test CloudEnv with.

```go
package main
import "fmt"
import "os"
func main() {
    fmt.Println(os.Getenv("FOO"))
}
```

But if you run this now you would get nothing:

```console
$ eval $(cloudenv source) && go run hello.go

```

That's because we haven't created the CloudEnv environment variable yet.

So the next step is initializing the app:

```console
$ cloudenv init
Name of App: gotest

==> SUCCESS: You have created the app 'gotest' in CloudEnv. Try the following command next:

EDITOR=nano cloudenv edit

==> REMEMBER: You need to distribute the following file to all your team members and deployment servers

/home/lucas/gotest/.cloudenv-secret-key
```

And now you can modify your environmental variables using `cloudenv edit`

```console
$ cloudenv edit
FOO=bar
```

Finally, we can get the output we expect.

```console
$ eval $(cloudenv source) && go run hello.go
bar
```
