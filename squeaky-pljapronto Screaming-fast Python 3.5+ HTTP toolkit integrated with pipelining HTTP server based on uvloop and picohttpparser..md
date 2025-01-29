---
Description: " squeaky-pl/japronto: Screaming-fast Python 3.5+ HTTP toolkit integrated with pipelining HTTP server based on uvloop and picohttpparser."
Notes: Screaming-fast Python 3.5+ HTTP toolkit integrated with pipelining HTTP server based on uvloop and picohttpparser. - squeaky-pl/japronto
author: 
Url: https://github.com/squeaky-pl/japronto
Created: 2025-01-29  03:12:24
Modified: 
tags:
---

# squeaky-pl/japronto: Screaming-fast Python 3.5+ HTTP toolkit integrated with pipelining HTTP server based on uvloop and picohttpparser.

source: https://github.com/squeaky-pl/japronto

> ## Excerpt
> Screaming-fast Python 3.5+ HTTP toolkit integrated with pipelining HTTP server based on uvloop and picohttpparser. - squeaky-pl/japronto

---
## Japronto!

[![irc: #japronto](https://camo.githubusercontent.com/ffb88bfe6631999266a81cf1b254a9499260da7cce738cdeee0ce502d95426cc/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6972632d2532336a6170726f6e746f2d627269676874677265656e2e737667)](https://webchat.freenode.net/?channels=japronto) [![Gitter japronto/Lobby](https://camo.githubusercontent.com/98ff1dd6377c3795553ebfc7a93aa41ecb68fd463c7ad8bbde1fc52a0bd194fa/68747470733a2f2f6261646765732e6769747465722e696d2f6a6170726f6e746f2f4c6f6262792e737667)](https://gitter.im/japronto/Lobby) [![Build Status](https://camo.githubusercontent.com/eed190fa24e61ecf611c8143a6e4db47ede1df8f4a36b15e233076b70a7a1f7b/68747470733a2f2f7472617669732d63692e6f72672f73717565616b792d706c2f6a6170726f6e746f2e7376673f6272616e63683d6d6173746572)](https://travis-ci.org/squeaky-pl/japronto) [![PyPI](https://camo.githubusercontent.com/14e330744167801ec4e5bfa8134038a562b4e4d9e032cef78f8a868164409470/68747470733a2f2f696d672e736869656c64732e696f2f707970692f762f6a6170726f6e746f2e737667)](https://pypi.python.org/pypi/japronto) [![PyPI version](https://camo.githubusercontent.com/1b14cb06b03065e82185a9be596b3d41a4003fd17dbf1e7a6064b3a01ef17cf8/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f6a6170726f6e746f2e737667)](https://pypi.python.org/pypi/japronto/)

**There is no new project development happening at the moment, but it's not abandoned either. Pull requests and new maintainers are welcome**.

**If you are a novice Python programmer, you don't like plumbing yourself or you don't have basic understanding of C, this project is not probably what you are looking for**.

Japronto (from Portuguese "já pronto" /ˈʒa pɾõtu/ meaning "already done") is a **screaming-fast**, **scalable**, **asynchronous** Python 3.5+ HTTP **toolkit** integrated with **pipelining HTTP server** based on [uvloop](https://github.com/MagicStack/uvloop) and [picohttpparser](https://github.com/h2o/picohttpparser). It's targeted at speed enthusiasts, people who like plumbing and early adopters.

You can read more in the [release announcement on medium](https://medium.com/@squeaky_pl/million-requests-per-second-with-python-95c137af319)

## Performance

Here's a chart to help you imagine what kind of things you can do with Japronto:

[![Requests per second](https://github.com/squeaky-pl/japronto/raw/master/benchmarks/results.png)](https://github.com/squeaky-pl/japronto/blob/master/benchmarks/results.png)

As user @heppu points out Go’s stdlib HTTP server can be 12% faster than the graph shows when written more carefully. Also there is the awesome fasthttp server for Go that apparently is only 18% slower than Japronto in this particular benchmark. Awesome! For details see [#12](https://github.com/squeaky-pl/japronto/pull/12) and [#14](https://github.com/squeaky-pl/japronto/pull/14).

These results of a simple "Hello world" application were obtained on AWS c4.2xlarge instance. To be fair all the contestants (including Go) were running single worker process. Servers were load tested using [wrk](https://github.com/wg/wrk) with 1 thread, 100 connections and 24 simultaneous (pipelined) requests per connection (cumulative parallelism of 2400 requests).

The source code for the benchmark can be found in [benchmarks](https://github.com/squeaky-pl/japronto/blob/master/benchmarks) directory.

The server is written in hand tweaked C trying to take advantage of modern CPUs. It relies on picohttpparser for header & chunked-encoding parsing while uvloop provides asynchronous I/O. It also tries to save up on system calls by combining writes together when possible.

## Early preview

This is an early preview with alpha quality implementation. APIs are provisional meaning that they will change between versions and more testing is needed. Don't use it for anything serious for now and definitely don't use it in production. Please try it though and report back feedback. If you are shopping for your next project's framework I would recommend [Sanic](https://github.com/channelcat/sanic).

At the moment the work is focused on CPython but I have PyPy on my radar, though I am not gonna look into it until PyPy reaches 3.5 compatibility somewhere later this year and most known JIT regressions are removed.

## Hello world

Here is how a simple web application looks like in Japronto:

```python
from japronto import Application


def hello(request):
    return request.Response(text='Hello world!')


app = Application()
app.router.add_route('/', hello)
app.run(debug=True)
```

## Tutorial

1.  [Getting started](https://github.com/squeaky-pl/japronto/blob/master/tutorial/1_hello.md)
2.  [Asynchronous handlers](https://github.com/squeaky-pl/japronto/blob/master/tutorial/2_async.md)
3.  [Router](https://github.com/squeaky-pl/japronto/blob/master/tutorial/3_router.md)
4.  [Request object](https://github.com/squeaky-pl/japronto/blob/master/tutorial/4_request.md)
5.  [Response object](https://github.com/squeaky-pl/japronto/blob/master/tutorial/5_response.md)
6.  [Handling exceptions](https://github.com/squeaky-pl/japronto/blob/master/tutorial/6_exceptions.md)
7.  [Extending request](https://github.com/squeaky-pl/japronto/blob/master/tutorial/7_extend.md)

## Features

-   HTTP 1.x implementation with support for chunked uploads
-   Full support for HTTP pipelining
-   Keep-alive connections with configurable reaper
-   Support for synchronous and asynchronous views
-   Master-multiworker model based on forking
-   Support for code reloading on changes
-   Simple routing

## License

This software is distributed under [MIT License](https://en.wikipedia.org/wiki/MIT_License). This is a very permissive license that lets you use this software for any commercial and non-commercial work. Full text of the license is included in [LICENSE.txt](https://github.com/squeaky-pl/japronto/blob/master/LICENSE.txt) file.

The source distribution of this software includes a copy of picohttpparser which is distributed under MIT license as well.
