---
Description: "psf/requests: A simple, yet elegant, HTTP library.Notes: A simple, yet elegant, HTTP library. Contribute to psf/requests development by creating an account on GitHub."
author: 
Url: https://github.com/psf/requests
Created: 2025-01-29  03:12:06
Modified: 
tags:
---

# psf/requests: A simple, yet elegant, HTTP library.

source: https://github.com/psf/requests

> ## Excerpt
> A simple, yet elegant, HTTP library. Contribute to psf/requests development by creating an account on GitHub.

---
## Requests

**Requests** is a simple, yet elegant, HTTP library.

```python
>>> import requests
>>> r = requests.get('https://httpbin.org/basic-auth/user/pass', auth=('user', 'pass'))
>>> r.status_code
200
>>> r.headers['content-type']
'application/json; charset=utf8'
>>> r.encoding
'utf-8'
>>> r.text
'{"authenticated": true, ...'
>>> r.json()
{'authenticated': True, ...}
```

Requests allows you to send HTTP/1.1 requests extremely easily. There’s no need to manually add query strings to your URLs, or to form-encode your `PUT` & `POST` data — but nowadays, just use the `json` method!

Requests is one of the most downloaded Python packages today, pulling in around `30M downloads / week`— according to GitHub, Requests is currently [depended upon](https://github.com/psf/requests/network/dependents?package_id=UGFja2FnZS01NzA4OTExNg%3D%3D) by `1,000,000+` repositories. You may certainly put your trust in this code.

[![Downloads](https://camo.githubusercontent.com/418ea710baac14c25ddb489ea3c0ff5055e2849cabc7e7206ca9141bd1631abd/68747470733a2f2f7374617469632e706570792e746563682f62616467652f72657175657374732f6d6f6e7468)](https://pepy.tech/project/requests) [![Supported Versions](https://camo.githubusercontent.com/88724c02528e664569d586017d412bcae7233c289e7f54055d7601f29d263856/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f72657175657374732e737667)](https://pypi.org/project/requests) [![Contributors](https://camo.githubusercontent.com/4e9a3a4e1a1097c5045114c214c02f88759c9c9a34a0a7b0cfd99f2c57b8bbbc/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6e7472696275746f72732f7073662f72657175657374732e737667)](https://github.com/psf/requests/graphs/contributors)

## Installing Requests and Supported Versions

Requests is available on PyPI:

```shell
$ python -m pip install requests
```

Requests officially supports Python 3.8+.

## Supported Features & Best–Practices

Requests is ready for the demands of building robust and reliable HTTP–speaking applications, for the needs of today.

-   Keep-Alive & Connection Pooling
-   International Domains and URLs
-   Sessions with Cookie Persistence
-   Browser-style TLS/SSL Verification
-   Basic & Digest Authentication
-   Familiar `dict`–like Cookies
-   Automatic Content Decompression and Decoding
-   Multi-part File Uploads
-   SOCKS Proxy Support
-   Connection Timeouts
-   Streaming Downloads
-   Automatic honoring of `.netrc`
-   Chunked HTTP Requests

[![Read the Docs](https://raw.githubusercontent.com/psf/requests/main/ext/ss.png)](https://requests.readthedocs.io/)

## Cloning the repository

When cloning the Requests repository, you may need to add the `-c fetch.fsck.badTimezone=ignore` flag to avoid an error about a bad commit (see [this issue](https://github.com/psf/requests/issues/2690) for more background):

```shell
git clone -c fetch.fsck.badTimezone=ignore https://github.com/psf/requests.git
```

You can also apply this setting to your global Git config:

```shell
git config --global fetch.fsck.badTimezone ignore
```

___

[![Kenneth Reitz](https://raw.githubusercontent.com/psf/requests/main/ext/kr.png)](https://kennethreitz.org/) [![Python Software Foundation](https://raw.githubusercontent.com/psf/requests/main/ext/psf.png)](https://www.python.org/psf)
