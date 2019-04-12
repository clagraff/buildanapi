---
title:   Your First Program
isChild: true
anchor:  your_first_program
---

## Your First Program {#your_first_program}

Let's create, build, and run a simple program in Golang. You will need to have
properly installed Golang in order to do all the steps.

Let's look at the code:

{% highlight golang %}
package main

import (
	"fmt"
)

func main() {
	fmt.Println("Hello, world!")
}
{% endhighlight %}

Now, you can build (read: compile) your program for your system.

{% highlight console %}
> go build main.go
> ls
main.exe
{% endhighlight %}

(note that the specific binary built will depend on your operating system)

Next, let's run our compiled binary!

{% highlight console %}
> ./main.exe
Hello, world!
{% endhighlight %}

## Two-in-One {#two_in_one}

Golang makes it easy to both build and run your application at once. Instead
of doing the two steps manually, we can use the `go run [FILE]` command.

Let's try it!

{% highlight console %}
> go run main.go
Hello, world!
{% endhighlight %}

Excellent!
