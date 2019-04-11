---
title:   Hello World
isChild: true
anchor:  hello_world
---

## Hello World {#hello_world}

Our goal now is to create a _very_ simple web server which will always
respond with an HTTP status code of `200` and a response body of `Hello World`.

The entire code snippet will be shown below; after it we will break down
the individual elements.

{% highlight golang %}
package main

import (
	"fmt"
	"net/http"
)

const port = ":8080"

func serveRequest(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintln(w, "Helo world")
}

func main() {
	fmt.Printf("Server listening on port: %s\n", port)

	http.HandleFunc("/", serveRequest)

	err := http.ListenAndServe(port, nil)
	if err != nil {
		panic(err)
	}
}

{% endhighlight %}

## Serving basic requests {#serving_basic_requests}

Let's look at our handler function, `serveRequest`:

{% highlight golang %}
func serveRequest(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintln(w, "Helo world")
}
{% endhighlight %}

This function will be called automatically when requests are received by our
HTTP server. It's job is to generate a response for each request.

When called, `serveRequest` will be given a
[ResponseWriter](https://golang.org/pkg/net/http/#ResponseWriter) and a
[Request](https://golang.org/pkg/net/http/#Request) reference as arguments.

The `ResponseWriter` is an interface used to construct responses; you can set
HTTP status codes, write to the response body, and manage response headers.

The `Request` reference points to the request currently being served. It
has information on the request, including provided content, the HTTP method used,
URL requested, and more.
