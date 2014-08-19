make-http
=========

This is a [Madefile](https://github.com/singron/madefile) for writing http
servers using Makefiles. It's a little like CGI, but entirely in make.

Example
-------

First setup make-http.

```make
# using madefile
$(call madefile-include,github.com/singron/make-http)
# or not
include path-to-make-http

MAKEHTTP_PORT = 8080 # the default

$(make-http-start)
```

Define a recipe that gives useful output.

```make
helloworld:
    @echo hello world!
```

This will expose an http endpoint at `http://localhost:8080/helloworld`

Start the server

```bash
$ make
```

Request useful output from the server.

```bash
$ curl localhost:8080/helloworld
hello world!
```

Requirements
------------

This uses GNU guile pretty heavily (make 4.0+ configured `--with-guile`).
