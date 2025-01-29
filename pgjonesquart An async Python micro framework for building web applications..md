---
Description: pgjones/quart: An async Python micro framework for building web applications.
Notes: An async Python micro framework for building web applications.  - pgjones/quart: An async Python micro framework for building web applications.
author: 
Url: https://github.com/pgjones/quart
Created: "2025-01-29  03:12:36"
Modified: 
Tags:
---

# pgjones/quart: An async Python micro framework for building web applications.

source: https://github.com/pgjones/quart

> ## Excerpt
> An async Python micro framework for building web applications.  - pgjones/quart: An async Python micro framework for building web applications.

---
## Quart

[![Quart logo](https://raw.githubusercontent.com/pallets/quart/main/artwork/logo.png)](https://raw.githubusercontent.com/pallets/quart/main/artwork/logo.png)

 [![Build Status](https://github.com/pallets/quart/actions/workflows/tests.yaml/badge.svg)](https://github.com/pallets/quart/commits/main)[![docs](https://camo.githubusercontent.com/265015f27268d18bf02b5b00fc7e2c9a06ec2150010362bc401da4bdbe6b1da0/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646f63732d70617373696e672d627269676874677265656e2e737667) ](https://quart.palletsprojects.com/)[![pypi](https://camo.githubusercontent.com/6970e14add5daff3bb65ef9ce2179dea60549778912140d2f78dfe9f28faabff/68747470733a2f2f696d672e736869656c64732e696f2f707970692f762f71756172742e737667) ](https://pypi.python.org/pypi/Quart/)[![python](https://camo.githubusercontent.com/1dda492255353ae54508f7ee34165cf147b508c222c4f93ce327c7f0313301bb/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f71756172742e737667) ](https://pypi.python.org/pypi/Quart/)[![license](https://camo.githubusercontent.com/6581c31c16c1b13ddc2efb92e2ad69a93ddc4a92fd871ff15d401c4c6c9155a4/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6c6963656e73652d4d49542d626c75652e737667) ](https://github.com/pallets/quart/blob/main/LICENSE)[![chat](https://camo.githubusercontent.com/97837b97dfb1f69c66f57d3782e30598c1c1358fe1aef05c67cc3a5cf1d6c15f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f636861742d6a6f696e5f6e6f772d627269676874677265656e2e737667)](https://discord.gg/pallets)

Quart is an async Python web microframework. Using Quart you can,

-   render and serve HTML templates,
-   write (RESTful) JSON APIs,
-   serve WebSockets,
-   stream request and response data,
-   do pretty much anything over the HTTP or WebSocket protocols.

## Quickstart

Quart can be installed via [pip](https://docs.python.org/3/installing/index.html),

and requires Python 3.7.0 or higher (see [python version support](https://quart.palletsprojects.com/en/latest/discussion/python_versions.html) for reasoning).

A minimal Quart example is,

```python
from quart import Quart, render_template, websocket

app = Quart(__name__)

@app.route("/")
async def hello():
    return await render_template("index.html")

@app.route("/api")
async def json():
    return {"hello": "world"}

@app.websocket("/ws")
async def ws():
    while True:
        await websocket.send("hello")
        await websocket.send_json({"hello": "world"})

if __name__ == "__main__":
    app.run()
```

if the above is in a file called `app.py` it can be run as,

To deploy this app in a production setting see the [deployment](https://quart.palletsprojects.com/en/latest/tutorials/deployment.html) documentation.

## Contributing

Quart is developed on [GitHub](https://github.com/pallets/quart). If you come across an issue, or have a feature request please open an [issue](https://github.com/pallets/quart/issues). If you want to contribute a fix or the feature-implementation please do (typo fixes welcome), by proposing a [merge request](https://github.com/pallets/quart/merge_requests).

### Testing

The best way to test Quart is with [Tox](https://tox.readthedocs.io/),

this will check the code style and run the tests.

## Help

The Quart [documentation](https://quart.palletsprojects.com/) or [cheatsheet](https://quart.palletsprojects.com/en/latest/reference/cheatsheet.html) are the best places to start, after that try searching [stack overflow](https://stackoverflow.com/questions/tagged/quart) or ask for help [on discord](https://discord.gg/pallets). If you still can't find an answer please [open an issue](https://github.com/pallets/quart/issues).

## Relationship with Flask

Quart is an asyncio reimplementation of the popular [Flask](http://flask.pocoo.org/) microframework API. This means that if you understand Flask you understand Quart.

Like Flask Quart has an ecosystem of extensions for more specific needs. In addition a number of the Flask extensions work with Quart.

### Migrating from Flask

It should be possible to migrate to Quart from Flask by a find and replace of `flask` to `quart` and then adding `async` and `await` keywords. See the [docs](https://quart.palletsprojects.com/en/latest/how_to_guides/flask_migration.html) for more help.
