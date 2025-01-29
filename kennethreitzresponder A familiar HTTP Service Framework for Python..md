---
Description: "kennethreitz/responder: A familiar HTTP Service Framework for Python."
Notes: A familiar HTTP Service Framework for Python. Contribute to kennethreitz/responder development by creating an account on GitHub.
author: 
Url: https://github.com/kennethreitz/responder
Created: 2025-01-29  03:12:13
Modified: 
tags:
---

# kennethreitz/responder: A familiar HTTP Service Framework for Python.

source: https://github.com/kennethreitz/responder

> ## Excerpt
> A familiar HTTP Service Framework for Python. Contribute to kennethreitz/responder development by creating an account on GitHub.

---
## Responder: a familiar HTTP Service Framework for Python

[![ci-tests](https://github.com/kennethreitz/responder/actions/workflows/test.yaml/badge.svg)](https://github.com/kennethreitz/responder/actions/workflows/test.yaml) [![ci-docs](https://github.com/kennethreitz/responder/actions/workflows/docs.yaml/badge.svg)](https://github.com/kennethreitz/responder/actions/workflows/docs.yaml) [![Documentation Status](https://github.com/kennethreitz/responder/actions/workflows/pages/pages-build-deployment/badge.svg)](https://responder.kennethreitz.org/) [![version](https://camo.githubusercontent.com/38f7d2fe4af2f1967f1e2be6f0ba91172ab1031d0244c8773272b9b979240fe6/68747470733a2f2f696d672e736869656c64732e696f2f707970692f762f726573706f6e6465722e737667)](https://pypi.org/project/responder/) [![license](https://camo.githubusercontent.com/68cb82b3e16ffaa4013cf950da96d0f9725ccaa9787b256064bacd5affe760d9/68747470733a2f2f696d672e736869656c64732e696f2f707970692f6c2f726573706f6e6465722e737667)](https://pypi.org/project/responder/) [![python-versions](https://camo.githubusercontent.com/b389a015a136dcf5dc0cbb798ce633f9591857c752b4a0b7932e8910429eea03/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f726573706f6e6465722e737667)](https://pypi.org/project/responder/) [![downloads](https://camo.githubusercontent.com/33e868d0425f2140f6dc3da5452922d12c32ba6015d0c5f041f8f4551eded5d4/68747470733a2f2f7374617469632e706570792e746563682f62616467652f726573706f6e6465722f6d6f6e7468)](https://pepy.tech/project/responder) [![contributors](https://camo.githubusercontent.com/4d6d45ba8954c80f7f4661da03b393fad9221317d917473913e855f6a292e5d6/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6e7472696275746f72732f6b656e6e657468726569747a2f726573706f6e6465722e737667)](https://github.com/kennethreitz/responder/graphs/contributors) [![status](https://camo.githubusercontent.com/141ff7699e99547b22bebed32336f60948039904f5089bca10ae0921f2e0a570/68747470733a2f2f696d672e736869656c64732e696f2f707970692f7374617475732f726573706f6e6465722e737667)](https://pypi.org/project/responder/)

[![responder-synopsis](https://camo.githubusercontent.com/becfe3953bb68d84932fe6666f9bca79a81b81cd05dade13595ec926c256934f/68747470733a2f2f6661726d322e737461746963666c69636b722e636f6d2f313935392f34333735303038313337305f613465323037353264655f6f5f642e706e67)](https://responder.readthedocs.io/)

Responder is powered by [Starlette](https://www.starlette.io/). [View documentation](https://responder.readthedocs.io/).

Responder gets you an ASGI app, with a production static files server pre-installed, Jinja templating, and a production webserver based on uvloop, automatically serving up requests with gzip compression. The `async` declaration within the example program is optional.

## Testimonials

> "Pleasantly very taken with python-responder. [@kennethreitz](https://x.com/kennethreitz42) at his absolute best." —Rudraksh M.K.

> "ASGI is going to enable all sorts of new high-performance web services. It's awesome to see Responder starting to take advantage of that." — Tom Christie author of [Django REST Framework](https://www.django-rest-framework.org/)

> "I love that you are exploring new patterns. Go go go!" — Danny Greenfield, author of [Two Scoops of Django](https://www.feldroy.com/two-scoops-press#two-scoops-of-django)

## More Examples

See [the documentation's feature tour](https://responder.readthedocs.io/tour.html) for more details on features available in Responder.

## Installing Responder

Install the most recent stable release:

```
pip install --upgrade 'responder'
```

Include support for all extensions and interfaces:

```
pip install --upgrade 'responder[full]'
```

Individual optional installation extras are:

-   graphql: Adds GraphQL support via Graphene
-   openapi: Adds OpenAPI/Swagger interface support

Install package with CLI and GraphQL support:

```
uv pip install --upgrade 'responder[cli,graphql]'
```

Alternatively, install directly from the repository:

```
pip install 'responder[full] @ git+https://github.com/kennethreitz/responder.git'
```

Responder supports **Python 3.7+**.

## The Basic Idea

The primary concept here is to bring the niceties that are brought forth from both Flask and Falcon and unify them into a single framework, along with some new ideas I have. I also wanted to take some of the API primitives that are instilled in the Requests library and put them into a web framework. So, you'll find a lot of parallels here with Requests.

-   Setting `resp.content` sends back bytes.
-   Setting `resp.text` sends back unicode, while setting `resp.html` sends back HTML.
-   Setting `resp.media` sends back JSON/YAML (`.text`/`.html`/`.content` override this).
-   Case-insensitive `req.headers` dict (from Requests directly).
-   `resp.status_code`, `req.method`, `req.url`, and other familiar friends.

## Ideas

-   Flask-style route expression, with new capabilities -- all while using Python 3.6+'s new f-string syntax.
-   I love Falcon's "every request and response is passed into to each view and mutated" methodology, especially `response.media`, and have used it here. In addition to supporting JSON, I have decided to support YAML as well, as Kubernetes is slowly taking over the world, and it uses YAML for all the things. Content-negotiation and all that.
-   **A built in testing client that uses the actual Requests you know and love**.
-   The ability to mount other WSGI apps easily.
-   Automatic gzipped-responses.
-   In addition to Falcon's `on_get`, `on_post`, etc methods, Responder features an `on_request` method, which gets called on every type of request, much like Requests.
-   A production static file server is built-in.
-   Uvicorn built-in as a production web server. I would have chosen Gunicorn, but it doesn't run on Windows. Plus, Uvicorn serves well to protect against slowloris attacks, making nginx unnecessary in production.
-   GraphQL support, via Graphene. The goal here is to have any GraphQL query exposable at any route, magically.
-   Provide an official way to run webpack.

## Development

See [Development Sandbox](https://responder.kennethreitz.org/sandbox.html).

## Supported by

[![JetBrains logo.](https://camo.githubusercontent.com/10b97e557d8d32622250903852c1b2db59c5d29d431bc3b2a0e55301219150b7/68747470733a2f2f7265736f75726365732e6a6574627261696e732e636f6d2f73746f726167652f70726f64756374732f636f6d70616e792f6272616e642f6c6f676f732f6a6574627261696e732e737667)](https://jb.gg/OpenSourceSupport)

Special thanks to the kind people at JetBrains s.r.o. for supporting us with excellent development tooling.
