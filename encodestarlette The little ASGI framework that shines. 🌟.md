---
Description: "encode/starlette: The little ASGI framework that shines. 🌟"
Notes: The little ASGI framework that shines. 🌟. Contribute to encode/starlette development by creating an account on GitHub.
author: 
Url: https://github.com/encode/starlette
Created: 2025-01-29  03:11:44
Modified: 
tags:
---

# encode/starlette: The little ASGI framework that shines. 🌟

source: https://github.com/encode/starlette

> ## Excerpt
> The little ASGI framework that shines. 🌟. Contribute to encode/starlette development by creating an account on GitHub.

---
_✨ The little ASGI framework that shines. ✨_

___

[![Build Status](https://github.com/encode/starlette/workflows/Test%20Suite/badge.svg)](https://github.com/encode/starlette/actions) [![Package version](https://camo.githubusercontent.com/dad8a26dc7c69102450860dcde4afaa44e5b84db97e1a6034fb10775233cf09a/68747470733a2f2f62616467652e667572792e696f2f70792f737461726c657474652e737667)](https://pypi.python.org/pypi/starlette) [![Supported Python Version](https://camo.githubusercontent.com/62f782d363456622dffbf28bdff3809f760db45a34e9bac9b96daf30060f7bad/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f737461726c657474652e7376673f636f6c6f723d253233333444303538)](https://pypi.org/project/starlette)

___

**Documentation**: [](https://www.starlette.io/)[https://www.starlette.io](https://www.starlette.io/)

**Source Code**: [](https://github.com/encode/starlette)[https://github.com/encode/starlette](https://github.com/encode/starlette)

___

## Starlette

Starlette is a lightweight [ASGI](https://asgi.readthedocs.io/en/latest/) framework/toolkit, which is ideal for building async web services in Python.

It is production-ready, and gives you the following:

-   A lightweight, low-complexity HTTP web framework.
-   WebSocket support.
-   In-process background tasks.
-   Startup and shutdown events.
-   Test client built on `httpx`.
-   CORS, GZip, Static Files, Streaming responses.
-   Session and Cookie support.
-   100% test coverage.
-   100% type annotated codebase.
-   Few hard dependencies.
-   Compatible with `asyncio` and `trio` backends.
-   Great overall performance [against independent benchmarks](https://www.techempower.com/benchmarks/#hw=ph&test=fortune&l=zijzen-sf).

## Installation

You'll also want to install an ASGI server, such as [uvicorn](https://www.uvicorn.org/), [daphne](https://github.com/django/daphne/), or [hypercorn](https://hypercorn.readthedocs.io/en/latest/).

## Example

```python
from starlette.applications import Starlette
from starlette.responses import JSONResponse
from starlette.routing import Route


async def homepage(request):
    return JSONResponse({'hello': 'world'})

routes = [
    Route("/", endpoint=homepage)
]

app = Starlette(debug=True, routes=routes)
```

Then run the application using Uvicorn:

For a more complete example, see [encode/starlette-example](https://github.com/encode/starlette-example).

## Dependencies

Starlette only requires `anyio`, and the following are optional:

-   [`httpx`](https://www.python-httpx.org/) - Required if you want to use the `TestClient`.
-   [`jinja2`](https://jinja.palletsprojects.com/) - Required if you want to use `Jinja2Templates`.
-   [`python-multipart`](https://multipart.fastapiexpert.com/) - Required if you want to support form parsing, with `request.form()`.
-   [`itsdangerous`](https://itsdangerous.palletsprojects.com/) - Required for `SessionMiddleware` support.
-   [`pyyaml`](https://pyyaml.org/wiki/PyYAMLDocumentation) - Required for `SchemaGenerator` support.

You can install all of these with `pip install starlette[full]`.

## Framework or Toolkit

Starlette is designed to be used either as a complete framework, or as an ASGI toolkit. You can use any of its components independently.

```python
from starlette.responses import PlainTextResponse


async def app(scope, receive, send):
    assert scope['type'] == 'http'
    response = PlainTextResponse('Hello, world!')
    await response(scope, receive, send)
```

Run the `app` application in `example.py`:

```shell
$ uvicorn example:app
INFO: Started server process [11509]
INFO: Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
```

Run uvicorn with `--reload` to enable auto-reloading on code changes.

## Modularity

The modularity that Starlette is designed on promotes building re-usable components that can be shared between any ASGI framework. This should enable an ecosystem of shared middleware and mountable applications.

The clean API separation also means it's easier to understand each component in isolation.

___

_Starlette is [BSD licensed](https://github.com/encode/starlette/blob/master/LICENSE.md) code.  
Designed & crafted with care._  
— ⭐️ —
