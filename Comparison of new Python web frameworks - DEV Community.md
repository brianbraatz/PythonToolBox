---
Description: Comparison of new Python web frameworks - DEV Community
Notes: Python has become a popular option for building web services. Here's a list of 11 new web frameworks in Python that you should consider for your next project.
author: 
Url: https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7
Created: "2025-01-29  03:09:03"
Modified: 
Tags:
---

# Comparison of new Python web frameworks - DEV Community

source: https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7

> ## Excerpt
> Python has become a popular option for building web services. Here's a list of 11 new web frameworks in Python that you should consider for your next project.

---
Python has been the go to language for building web services, right from quick-and-dirty RESTful APIs to full-fledged web applications that serve millions of users. If you have been dabbling in this area, you'd have probably used some of the most popular web frameworks already — Django, Flask, Falcon, Tornado, CherryPy, among others.

In the last few years, though, there have been many new kids on the block. These new frameworks have taken a fresh approach with focus on performance and expressiveness of the API. Here’s a comparision of new web frameworks in Python that you should consider for your next side project.

You might also want to check out [DeepSource's static analysis for Python](https://deepsource.io/python-static-code-analysis/?utm_source=devto&utm_medium=organic&utm_campaign=contentdistribution&utm_term=pythonframeworks), that detects 600+ bug risks, anti-patterns, and security vulnerabilities in your Python code.

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#1-sanic)1\. Sanic

Sanic dubs itself as a web server and web framework that's written to go fast. It allows the usage of the `async` / `await` syntax added in Python 3.5, which makes your code non-blocking and speedy. Sanic makes use of `uvloop` and `ujson` to help with performance, but those packages are optional.

**Installation**

`pip install sanic`

**Hello world example**  

```
from sanic import Sanic
from sanic.response import json

app = Sanic()

@app.route('/')
async def test(request):
    return json({'hello': 'world'})

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=8000)
```

[Sanic on GitHub »](https://github.com/huge-success/sanic)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#2-starlette)2\. Starlette

Starlette is a lightweight [ASGI](https://asgi.readthedocs.io/en/latest/) framework which is ideal for building high performance `asyncio` services, designed to be used either as a complete framework, or as an ASGI toolkit. With some batteries included, it has support for WebSockets, GraphQL, in-process background tasks, and a test client built on [requests](https://github.com/psf/requests).

**Installation**

`pip install starlette`

**Hello world example**  

```
from starlette.applications import Starlette
from starlette.responses import JSONResponse
import uvicorn

app = Starlette(debug=True)


@app.route('/')
async def homepage(request):
    return JSONResponse({'hello': 'world'})

if __name__ == '__main__':
    uvicorn.run(app, host='0.0.0.0', port=8000)
```

[Starlette on GitHub »](https://github.com/encode/starlette)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#3-masonite)3\. Masonite

Masonite is a developer centric Python web framework that strives for an actual batteries included developer tool with a lot of out of the box functionality with an extremely extensible architecture. It has a simple and expressive routing engine, a simple migration system that removes the "magic" and finger crossing of migrations, and a great Active Record style ORM called Orator.

**Installation**

`pip install masonite-cli`

[Masonite on GitHub »](https://github.com/MasoniteFramework/masonite)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#4-fastapi)4\. FastAPI

FastAPI is a modern, high-performance, web framework for building APIs with Python 3.6+ based on standard Python type hints. It is built on top of Starlette, and is one of the fastest Python frameworks available. Based on, and fully compatible with, the open standards for APIs — [OpenAPI](https://github.com/OAI/OpenAPI-Specification) (previously known as Swagger) and [JSON Schema](http://json-schema.org/).

**Installation**

`pip install fastapi`

**Hello world example**  

```
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}
```

[FastAPI on GitHub »](https://github.com/tiangolo/fastapi)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#5-responder)5\. Responder

Also based on Starlette, Responder's primary concept is to bring the niceties that are brought forth from both Flask and Falcon and unify them into a single framework. It has a production static file server is built-in, automatic gzipped-responses, native GraphQL support, and a built-in testing client that uses [requests](https://github.com/psf/requests).

**Installation**

`pip install responder`

**Hello world example**  

```
import responder

api = responder.API()

@api.route("/{greeting}")
async def greet_world(req, resp, *, greeting):
    resp.text = f"{greeting}, world!"

if __name__ == '__main__':
    api.run()
```

[Responder on GitHub »](https://github.com/taoufik07/responder)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#6-molten)6\. Molten

Molten is a minimal, extensible, fast and productive framework for building HTTP APIs with Python. Molten can automatically validate requests according to predefined schemas, ensuring that your handlers only ever run if given valid input. Molten also has support for a function-based middleware, dependency injection, and includes the `molten.contrib` package which contains various functionality commonly required by APIs in the real world such as configuration files, Prometheus metrics, request IDs, sessions, SQLAlchemy, templating, websockets and more.

**Installation**

`pip install molten`

**Hello world example**  

```
from molten import App, Route

def hello(name: str) -&gt; str:
    return f"Hello {name}!"

app = App(routes=[Route("/hello/{name}", hello)])
```

[Molten on GitHub »](https://github.com/Bogdanp/molten)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#7-japronto)7\. Japronto

Japronto is a screaming-fast, scalable, asynchronous Python 3.5+ HTTP toolkit integrated with pipelining HTTP server based on uvloop and picohttpparser. It’s targeted at speed enthusiasts, people who like plumbing and early adopters. There is no new project development happening at the moment, but it’s not abandoned either.

**Installation**

`pip install japronto`

**Hello world example**  

```
from japronto import Application

def hello(request):
    return request.Response(text='Hello world!')

app = Application()
app.router.add_route('/', hello)
app.run(debug=True)
```

[Japronto on GitHub »](https://github.com/squeaky-pl/japronto)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#8-klein)8\. Klein

Klein is a micro-framework for developing production-ready web services with Python. It is ‘micro’ in that it has an incredibly small API similar to Bottle and Flask. It is not ‘micro’ in that it depends on things outside the standard library. This is primarily because it is built on widely used and well tested components like Werkzeug and Twisted.

**Installation**

`pip install klein`

**Hello world example**  

```
from klein import run, route

@route('/')
def home(request):
    return 'Hello, world!'

run("localhost", 8080)
```

[Klein on GitHub »](https://github.com/twisted/klein)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#9-quart)9\. Quart

Quart is a Python ASGI web microframework. It is intended to provide the easiest way to use asyncio functionality in a web context, especially with existing Flask apps. This is possible as the Quart API is a superset of the Flask API. Quart aims to be a complete web microframework, as it supports HTTP/1.1, HTTP/2 and websockets.

**Installation**

`pip install quart`

**Hello world example**  

```
rom quart import Quart, websocket

app = Quart(__name__)

@app.route('/')
async def hello():
    return 'hello'

@app.websocket('/ws')
async def ws():
    while True:
        await websocket.send('hello')

app.run()
```

[Quart on GitHub »](https://github.com/pgjones/quart)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#10-blacksheep)10\. BlackSheep

BlackSheep is an asynchronous web framework to build event based, non-blocking Python web applications. It is inspired by Flask and ASP.NET Core. BlackSheep supports automatic binding of values for request handlers, by type annotation or by conventions. It also supports dependency injection, and implements strategies to handle authentication and authorization using external libraries.

**Installation**

`pip install blacksheep`

**Hello world example**  

```
from datetime import datetime
from blacksheep.server import Application
from blacksheep.server.responses import text

app = Application()

@app.route('/')
async def home(request):
    return text(f'Hello, World! {datetime.utcnow().isoformat()}')
```

[BlackSheep on GitHub »](https://github.com/RobertoPrevato/BlackSheep)

## [](https://dev.to/deepsource/comparison-of-new-python-web-frameworks-bn7#11-cyclone)11\. Cyclone

Cyclone is a web server framework that implements the Tornado API as a Twisted protocol. The idea is to bridge Tornado’s elegant and straightforward API to Twisted’s Event-Loop, enabling a vast number of supported protocols. This combination provides the ground for building up hybrid servers capable of handling HTTP very efficiently while also serve or use e-mail, ssh, sip, irc, etc, all concurrently.

**Installation**

`pip install cyclone`

[Cyclone on GitHub »](https://github.com/fiorix/cyclone)
