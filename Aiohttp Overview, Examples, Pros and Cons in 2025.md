---
Description: Aiohttp Overview, Examples, Pros and Cons in 2025
Notes: Compare Aiohttp with alternative projects. View features, pros, cons, and usage examples.
author: 
Url: https://best-of-web.builder.io/library/aio-libs/aiohttp
Created: "2025-01-29  03:05:38"
Modified: 
Tags:
---

# Aiohttp Overview, Examples, Pros and Cons in 2025

source: https://best-of-web.builder.io/library/aio-libs/aiohttp

> ## Excerpt
> Compare Aiohttp with alternative projects. View features, pros, cons, and usage examples.

---
## \================================== Async http client/server framework

.. image:: [https://raw.githubusercontent.com/aio-libs/aiohttp/master/docs/aiohttp-plain.svg](https://raw.githubusercontent.com/aio-libs/aiohttp/master/docs/aiohttp-plain.svg) :height: 64px :width: 64px :alt: aiohttp logo

|

.. image:: [https://github.com/aio-libs/aiohttp/workflows/CI/badge.svg](https://github.com/aio-libs/aiohttp/workflows/CI/badge.svg) :target: [https://github.com/aio-libs/aiohttp/actions?query=workflow%3ACI](https://github.com/aio-libs/aiohttp/actions?query=workflow%3ACI) :alt: GitHub Actions status for master branch

.. image:: [https://codecov.io/gh/aio-libs/aiohttp/branch/master/graph/badge.svg](https://codecov.io/gh/aio-libs/aiohttp/branch/master/graph/badge.svg) :target: [https://codecov.io/gh/aio-libs/aiohttp](https://codecov.io/gh/aio-libs/aiohttp) :alt: codecov.io status for master branch

.. image:: [https://img.shields.io/endpoint?url=https://codspeed.io/badge.json](https://img.shields.io/endpoint?url=https://codspeed.io/badge.json) :target: [https://codspeed.io/aio-libs/aiohttp](https://codspeed.io/aio-libs/aiohttp) :alt: Codspeed.io status for aiohttp

.. image:: [https://badge.fury.io/py/aiohttp.svg](https://badge.fury.io/py/aiohttp.svg) :target: [https://pypi.org/project/aiohttp](https://pypi.org/project/aiohttp) :alt: Latest PyPI package version

.. image:: [https://img.shields.io/pypi/dm/aiohttp](https://img.shields.io/pypi/dm/aiohttp) :target: [https://pypistats.org/packages/aiohttp](https://pypistats.org/packages/aiohttp) :alt: Downloads count

.. image:: [https://readthedocs.org/projects/aiohttp/badge/?version=latest](https://readthedocs.org/projects/aiohttp/badge/?version=latest) :target: [https://docs.aiohttp.org/](https://docs.aiohttp.org/) :alt: Latest Read The Docs

.. image:: [https://img.shields.io/matrix/aio-libs:matrix.org?label=Discuss%20on%20Matrix%20at%20%23aio-libs%3Amatrix.org&logo=matrix&server\_fqdn=matrix.org&style=flat](https://img.shields.io/matrix/aio-libs:matrix.org?label=Discuss%20on%20Matrix%20at%20%23aio-libs%3Amatrix.org&logo=matrix&server_fqdn=matrix.org&style=flat) :target: [https://matrix.to/#/%23aio-libs:matrix.org](https://matrix.to/#/%23aio-libs:matrix.org) :alt: Matrix Room â #aio-libs:matrix.org

.. image:: [https://img.shields.io/matrix/aio-libs-space:matrix.org?label=Discuss%20on%20Matrix%20at%20%23aio-libs-space%3Amatrix.org&logo=matrix&server\_fqdn=matrix.org&style=flat](https://img.shields.io/matrix/aio-libs-space:matrix.org?label=Discuss%20on%20Matrix%20at%20%23aio-libs-space%3Amatrix.org&logo=matrix&server_fqdn=matrix.org&style=flat) :target: [https://matrix.to/#/%23aio-libs-space:matrix.org](https://matrix.to/#/%23aio-libs-space:matrix.org) :alt: Matrix Space â #aio-libs-space:matrix.org

## Key Features

-   Supports both client and server side of HTTP protocol.
-   Supports both client and server Web-Sockets out-of-the-box and avoids Callback Hell.
-   Provides Web-server with middleware and pluggable routing.

## Getting started

## Client

To get something from the web:

.. code-block:: python

import aiohttp import asyncio

async def main():

```
  async with aiohttp.ClientSession() as session:
      async with session.get('http://python.org') as response:

          print("Status:", response.status)
          print("Content-type:", response.headers['content-type'])

          html = await response.text()
          print("Body:", html[:15], "...")
```

asyncio.run(main())

This prints:

.. code-block::

```
Status: 200
Content-type: text/html; charset=utf-8
Body: &lt;!doctype html&gt; ...
```

Coming from `requests <https://requests.readthedocs.io/>`\_ ? Read `why we need so many lines <https://aiohttp.readthedocs.io/en/latest/http_request_lifecycle.html>`\_.

## Server

An example using a simple server:

.. code-block:: python

```
# examples/server_simple.py
from aiohttp import web

async def handle(request):
    name = request.match_info.get('name', "Anonymous")
    text = "Hello, " + name
    return web.Response(text=text)

async def wshandle(request):
    ws = web.WebSocketResponse()
    await ws.prepare(request)

    async for msg in ws:
        if msg.type == web.WSMsgType.text:
            await ws.send_str("Hello, {}".format(msg.data))
        elif msg.type == web.WSMsgType.binary:
            await ws.send_bytes(msg.data)
        elif msg.type == web.WSMsgType.close:
            break

    return ws


app = web.Application()
app.add_routes([web.get('/', handle),
                web.get('/echo', wshandle),
                web.get('/{name}', handle)])

if __name__ == '__main__':
    web.run_app(app)
```

## Documentation

[https://aiohttp.readthedocs.io/](https://aiohttp.readthedocs.io/)

## Demos

[https://github.com/aio-libs/aiohttp-demos](https://github.com/aio-libs/aiohttp-demos)

## External links

-   `Third party libraries <http://aiohttp.readthedocs.io/en/latest/third_party.html>`\_
-   `Built with aiohttp <http://aiohttp.readthedocs.io/en/latest/built_with.html>`\_
-   `Powered by aiohttp <http://aiohttp.readthedocs.io/en/latest/powered_by.html>`\_

Feel free to make a Pull Request for adding your link to these pages!

## Communication channels

_aio-libs Discussions_: [https://github.com/aio-libs/aiohttp/discussions](https://github.com/aio-libs/aiohttp/discussions)

_Matrix_: `#aio-libs:matrix.org <https://matrix.to/#/#aio-libs:matrix.org>`\_

We support `Stack Overflow <https://stackoverflow.com/questions/tagged/aiohttp>`\_. Please add _aiohttp_ tag to your question there.

## Requirements

-   multidict\_
-   yarl\_
-   frozenlist\_

Optionally you may install the aiodns\_ library (highly recommended for sake of speed).

.. \_aiodns: [https://pypi.python.org/pypi/aiodns](https://pypi.python.org/pypi/aiodns) .. \_multidict: [https://pypi.python.org/pypi/multidict](https://pypi.python.org/pypi/multidict) .. \_frozenlist: [https://pypi.org/project/frozenlist/](https://pypi.org/project/frozenlist/) .. \_yarl: [https://pypi.python.org/pypi/yarl](https://pypi.python.org/pypi/yarl)

## License

`aiohttp` is offered under the Apache 2 license.

## Keepsafe

The aiohttp community would like to thank Keepsafe ([https://www.getkeepsafe.com](https://www.getkeepsafe.com/)) for its support in the early days of the project.

## Source code

The latest developer version is available in a GitHub repository: [https://github.com/aio-libs/aiohttp](https://github.com/aio-libs/aiohttp)

## Benchmarks

If you are interested in efficiency, the AsyncIO community maintains a list of benchmarks on the official wiki: [https://github.com/python/asyncio/wiki/Benchmarks](https://github.com/python/asyncio/wiki/Benchmarks)
