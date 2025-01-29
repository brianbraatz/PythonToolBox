---
Description: "twisted/klein: werkzeug + twisted.web"
Notes: werkzeug + twisted.web. Contribute to twisted/klein development by creating an account on GitHub.
author: 
Url: https://github.com/twisted/klein
Created: 2025-01-29  03:12:29
Modified: 
tags:
---

# twisted/klein: werkzeug + twisted.web

source: https://github.com/twisted/klein

> ## Excerpt
> werkzeug + twisted.web. Contribute to twisted/klein development by creating an account on GitHub.

---
## Klein, a Web Micro-Framework

[![Build Status](https://github.com/twisted/klein/workflows/CI/badge.svg?branch=trunk)](https://github.com/twisted/klein/actions) [![Code Coverage](https://camo.githubusercontent.com/39174656dc1ce6e2d26dd64997728a6fc7d6ebfd2561ea1637e666a23d170866/68747470733a2f2f636f6465636f762e696f2f6769746875622f747769737465642f6b6c65696e2f636f7665726167652e7376673f6272616e63683d7472756e6b)](https://codecov.io/github/twisted/klein?branch=trunk) [![Python Version Compatibility](https://camo.githubusercontent.com/34cc9475f9219a96b7329afc2385042e0796420e5e7128c1182e81ff43dc3dfd/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f6b6c65696e2e737667)](https://pypi.org/project/klein)

Klein is a micro-framework for developing production-ready web services with Python. It is 'micro' in that it has an incredibly small API similar to [Bottle](https://bottlepy.org/docs/dev/index.html) and [Flask](https://flask.palletsprojects.com/). It is not 'micro' in that it depends on things outside the standard library. This is primarily because it is built on widely used and well tested components like [Werkzeug](https://werkzeug.palletsprojects.com/) and [Twisted](https://twisted.org/).

A [Klein bottle](https://en.wikipedia.org/wiki/Klein_bottle) is an example of a non-orientable surface, and a glass Klein bottle looks like a twisted bottle or twisted flask. This, of course, made it too good of a pun to pass up.

Klein's documentation can be found at [Read The Docs](https://klein.readthedocs.org/).

## Example

This is a sample Klein application that returns 'Hello, world!', running on port `8080`.

```python
from klein import run, route

@route('/')
def home(request):
    return 'Hello, world!'

run("localhost", 8080)
```

## Contribute

`klein` is hosted on [GitHub](https://github.com/twisted/klein) and is an open source project that welcomes contributions of all kinds from the community, including:

-   code patches,
-   [documentation](https://klein.readthedocs.org/) improvements,
-   [bug reports](https://github.com/twisted/klein/issues),
-   reviews for [contributed patches](https://github.com/twisted/klein/pulls).

For more information about contributing, see [the contributor guidelines](https://github.com/twisted/klein/tree/trunk/CONTRIBUTING.rst).
