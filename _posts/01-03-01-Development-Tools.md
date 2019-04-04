---
title:   Development Tools
isChild: true
anchor:  development_tools
---

## gofmt {#gofmt}

Gofmt is a tool which comes with Go; it allows you to format your code automatically.

Here is an example of using the code in act:

{% highlight golang %}
package     main

import   ("fmt")

func main() {
fmt.Print("Hello,")
        fmt.Print(  " world!\n" )
}


{% endhighlight %}

Let's run `gofmt` and see how it auto-formats our code:

{% highlight console %}
> gofmt main.go
main.go
> cat main.go
package main

import (
	"fmt"
)

func main() {
	fmt.Print("Hello,")
	fmt.Print(" world!\n")
}

{% endhighlight %}


## goimports {#goimports}

The `goimports` command does everything `go fmt` does, as well as automatically
add missing imports and remove unnecessary imports from your files.

Let's use the same file as last time, except the imports are messed up.

{% highlight golang %}
package     main

import   (
    "bytes"
  )

func main() {
fmt.Print("Hello,")
        fmt.Print(  " world!\n" )
}


{% endhighlight %}

If we use the `-w` flag, it will override the file instead of outputting the
corrected code, like so:

{% highlight console %}
> goimports -w main.go
> cat main.go
package main

import "fmt"

func main() {
	fmt.Print("Hello,")
	fmt.Print(" world!\n")
}

{% endhighlight %}
