---
Description: "Neoteroi/BlackSheep: Fast ASGI web framework for PythonNotes: Fast ASGI web framework for Python. Contribute to Neoteroi/BlackSheep development by creating an account on GitHub."
author: 
Url: https://github.com/Neoteroi/BlackSheep
Created: 2025-01-29  03:12:41
Modified: 
tags:
---

# Neoteroi/BlackSheep: Fast ASGI web framework for Python

source: https://github.com/Neoteroi/BlackSheep

> ## Excerpt
> Fast ASGI web framework for Python. Contribute to Neoteroi/BlackSheep development by creating an account on GitHub.

---
[![Build](https://github.com/Neoteroi/BlackSheep/workflows/Main/badge.svg)](https://github.com/Neoteroi/BlackSheep/actions) [![pypi](https://camo.githubusercontent.com/481d8a7b8a4c723aa9cb821029f670ff8aebdc863fa4f546d319d9b6b1f456e9/68747470733a2f2f696d672e736869656c64732e696f2f707970692f762f426c61636b53686565702e7376673f636f6c6f723d626c7565)](https://pypi.org/project/BlackSheep/) [![versions](https://camo.githubusercontent.com/89b16e7422a89a4abe483f2ffa61298f596dbedbb88b90ff336c901e6b84c1a3/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f626c61636b73686565702e737667)](https://github.com/robertoprevato/blacksheep) [![codecov](https://camo.githubusercontent.com/87863db79cd74aff24806f7e37a230bc9c65f7a88cbc0ba0794be0d8be7b2338/68747470733a2f2f636f6465636f762e696f2f67682f4e656f7465726f692f426c61636b53686565702f6272616e63682f6d61737465722f67726170682f62616467652e7376673f746f6b656e3d4e7a6932394c30456731)](https://codecov.io/gh/Neoteroi/BlackSheep) [![license](https://camo.githubusercontent.com/fdce659108f56dafe5a2541d4edfefa467652cbd11990f891bed2cdbdb9b2d09/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f4e656f7465726f692f626c61636b73686565702e737667)](https://github.com/Neoteroi/blacksheep/blob/main/LICENSE) [![Join the chat at https://gitter.im/Neoteroi/BlackSheep](https://camo.githubusercontent.com/1a0a968f9ae122b282cd00e0897badebd44d733a8ec4f8253de65d6d0d9c7efd/68747470733a2f2f6261646765732e6769747465722e696d2f4e656f7465726f692f426c61636b53686565702e737667)](https://gitter.im/Neoteroi/BlackSheep?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) [![documentation](https://camo.githubusercontent.com/3c4fd6be857df8314359d34258d5025f5495a5f11c7d3741339d57509962a26e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2546302539462539332539362d646f63732d707572706c65)](https://www.neoteroi.dev/blacksheep/)

## BlackSheep

BlackSheep is an asynchronous web framework to build event based web applications with Python. It is inspired by [Flask](https://palletsprojects.com/p/flask/), [ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/), and the work by [Yury Selivanov](https://magic.io/blog/uvloop-blazing-fast-python-networking/).

[![Black Sheep](https://camo.githubusercontent.com/c7e79fe8e0aff3402390c2557bac3394e15912873b53c025a56a119205acd22a/68747470733a2f2f7777772e6e656f7465726f692e6465762f626c61636b73686565702f696d672f626c61636b73686565702e706e67)](https://github.com/Neoteroi/BlackSheep#blacksheep)

___

```python
from datetime import datetime

from blacksheep import Application, get


app = Application()

@get("/")
async def home():
    return f"Hello, World! {datetime.utcnow().isoformat()}"
```

## Getting started using the CLI ✨

BlackSheep offers a CLI to bootstrap new projects rapidly. To try it, first install the `blacksheep-cli` package:

```shell
pip install blacksheep-cli
```

Then use the `blacksheep create` command to bootstrap a project using one of the supported templates.

[![blacksheep create command](https://gist.githubusercontent.com/RobertoPrevato/38a0598b515a2f7257c614938843b99b/raw/67d15ba337de94c2f50d980a7b8924a747259254/blacksheep-create-demo.gif)](https://gist.githubusercontent.com/RobertoPrevato/38a0598b515a2f7257c614938843b99b/raw/67d15ba337de94c2f50d980a7b8924a747259254/blacksheep-create-demo.gif)

The CLI includes a help, and supports custom templates, using the same sources supported by `Cookiecutter`.

## Getting started with the documentation

The documentation offers getting started tutorials:

-   [Getting started: basics](https://www.neoteroi.dev/blacksheep/getting-started/)
-   [Getting started: the MVC project template](https://www.neoteroi.dev/blacksheep/mvc-project-template/)

These project templates can be used to start new applications faster:

-   [MVC project template](https://github.com/Neoteroi/BlackSheepMVC)
-   [Empty project template](https://github.com/Neoteroi/BlackSheepEmptyProject)

## Requirements

[Python](https://www.python.org/): any version listed in the project's classifiers. The current list is:

[![versions](https://camo.githubusercontent.com/89b16e7422a89a4abe483f2ffa61298f596dbedbb88b90ff336c901e6b84c1a3/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f626c61636b73686565702e737667)](https://github.com/robertoprevato/blacksheep)

BlackSheep belongs to the category of [ASGI](https://asgi.readthedocs.io/en/latest/) web frameworks, so it requires an ASGI HTTP server to run, such as [uvicorn](http://www.uvicorn.org/), or [hypercorn](https://pgjones.gitlab.io/hypercorn/). For example, to use it with uvicorn:

To run an application like in the example above, use the methods provided by the ASGI HTTP Server:

```shell
# if the BlackSheep app is defined in a file `server.py`

$ uvicorn server:app
```

To run for production, refer to the documentation of the chosen ASGI server (i.e. for [uvicorn](https://www.uvicorn.org/#running-with-gunicorn)).

## Automatic bindings and dependency injection

BlackSheep supports automatic binding of values for request handlers, by type annotation or by conventions. See [more here](https://www.neoteroi.dev/blacksheep/requests/).

```python
from dataclasses import dataclass

from blacksheep import Application, FromJSON, FromQuery, get, post


app = Application()


@dataclass
class CreateCatInput:
    name: str


@post("/api/cats")
async def example(data: FromJSON[CreateCatInput]):
    # in this example, data is bound automatically reading the JSON
    # payload and creating an instance of `CreateCatInput`
    ...


@get("/:culture_code/:area")
async def home(culture_code, area):
    # in this example, both parameters are obtained from routes with
    # matching names
    return f"Request for: {culture_code} {area}"


@get("/api/products")
def get_products(
    page: int = 1,
    size: int = 30,
    search: str = "",
):
    # this example illustrates support for implicit query parameters with
    # default values
    # since the source of page, size, and search is not specified and no
    # route parameter matches their name, they are obtained from query string
    ...


@get("/api/products2")
def get_products2(
    page: FromQuery[int] = FromQuery(1),
    size: FromQuery[int] = FromQuery(30),
    search: FromQuery[str] = FromQuery(""),
):
    # this example illustrates support for explicit query parameters with
    # default values
    # in this case, parameters are explicitly read from query string
    ...
```

It also supports [dependency injection](https://www.neoteroi.dev/blacksheep/dependency-injection/), a feature that provides a consistent and clean way to use dependencies in request handlers.

## Generation of OpenAPI Documentation

[Generation of OpenAPI Documentation](https://www.neoteroi.dev/blacksheep/openapi/).

## Strategies to handle authentication and authorization

BlackSheep implements strategies to handle authentication and authorization. These features are documented here:

-   [Authentication](https://www.neoteroi.dev/blacksheep/authentication/)
-   [Authorization](https://www.neoteroi.dev/blacksheep/authorization/)

```python
app.use_authentication()\
    .add(ExampleAuthenticationHandler())


app.use_authorization()\
    .add(AdminsPolicy())


@auth("admin")
@get("/")
async def only_for_admins():
    ...


@auth()
@get("/")
async def only_for_authenticated_users():
    ...
```

Since version `1.2.1`, BlackSheep implements:

-   [Built-in support for OpenID Connect authentication](https://www.neoteroi.dev/blacksheep/authentication/#oidc)
-   [Built-in support for JWT Bearer authentication](https://www.neoteroi.dev/blacksheep/authentication/#jwt-bearer)

Meaning that it is easy to integrate with services such as:

-   [Auth0](https://auth0.com/)
-   [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)
-   [Azure Active Directory B2C](https://docs.microsoft.com/en-us/azure/active-directory-b2c/overview)
-   [Okta](https://www.okta.com/)

Refer to the documentation and to [BlackSheep-Examples](https://github.com/Neoteroi/BlackSheep-Examples) for more details and examples.

## Web framework features

-   [ASGI compatibility](https://www.neoteroi.dev/blacksheep/asgi/)
-   [Routing](https://www.neoteroi.dev/blacksheep/routing/)
-   Request handlers can be [defined as functions](https://www.neoteroi.dev/blacksheep/request-handlers/), or [class methods](https://www.neoteroi.dev/blacksheep/controllers/)
-   [Middlewares](https://www.neoteroi.dev/blacksheep/middlewares/)
-   [WebSocket](https://www.neoteroi.dev/blacksheep/websocket/)
-   [Server-Sent Events (SSE)](https://www.neoteroi.dev/blacksheep/server-sent-events/)
-   [Built-in support for dependency injection](https://www.neoteroi.dev/blacksheep/dependency-injection/)
-   [Support for automatic binding of route and query parameters to request handlers methods calls](https://www.neoteroi.dev/blacksheep/getting-started/#handling-route-parameters)
-   [Strategy to handle exceptions](https://www.neoteroi.dev/blacksheep/application/#configuring-exceptions-handlers)
-   [Strategy to handle authentication and authorization](https://www.neoteroi.dev/blacksheep/authentication/)
-   [Built-in support for OpenID Connect authentication using OIDC discovery](https://www.neoteroi.dev/blacksheep/authentication/#oidc)
-   [Built-in support for JWT Bearer authentication using OIDC discovery and other sources of JWKS](https://www.neoteroi.dev/blacksheep/authentication/#jwt-bearer)
-   [Handlers normalization](https://www.neoteroi.dev/blacksheep/request-handlers/)
-   [Serving static files](https://www.neoteroi.dev/blacksheep/static-files/)
-   [Integration with Jinja2](https://www.neoteroi.dev/blacksheep/templating/)
-   [Support for serving SPAs that use HTML5 History API for client side routing](https://www.neoteroi.dev/blacksheep/static-files/#how-to-serve-spas-that-use-html5-history-api)
-   [Support for automatic generation of OpenAPI Documentation](https://www.neoteroi.dev/blacksheep/openapi/)
-   [Strategy to handle CORS settings](https://www.neoteroi.dev/blacksheep/cors/)
-   [Sessions](https://www.neoteroi.dev/blacksheep/sessions/)
-   Support for automatic binding of `dataclasses` and [`pydantic`](https://pydantic-docs.helpmanual.io/) models to handle the request body payload expected by request handlers
-   [`TestClient` class to simplify testing of applications](https://www.neoteroi.dev/blacksheep/testing/)
-   [Anti Forgery validation](https://www.neoteroi.dev/blacksheep/anti-request-forgery) to protect against Cross-Site Request Forgery (XSRF/CSRF) attacks

## Client features

BlackSheep includes an HTTP Client.

**Example:**

```python
import asyncio

from blacksheep.client import ClientSession


async def client_example():
    async with ClientSession() as client:
        response = await client.get("https://docs.python.org/3/")
        text = await response.text()
        print(text)


asyncio.run(client_example())
```

## Supported platforms and runtimes

-   Python: all versions included in the build matrix
-   Ubuntu
-   Windows 10
-   macOS

## Documentation

Please refer to the [documentation website](https://www.neoteroi.dev/blacksheep/).

## Communication

[BlackSheep community in Gitter](https://gitter.im/Neoteroi/BlackSheep).

## Branches

The _main_ branch contains the currently developed version, which is version 2. The _v1_ branch contains version 1 of the web framework, for bugs fixes and maintenance.
