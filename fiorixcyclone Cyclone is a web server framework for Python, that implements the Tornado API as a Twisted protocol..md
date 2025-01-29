---
Description: fiorix/cyclone: Cyclone is a web server framework for Python, that implements the Tornado API as a Twisted protocol.
Notes: Cyclone is a web server framework for Python, that implements the Tornado API as a Twisted protocol. - fiorix/cyclone
author: 
Url: https://github.com/fiorix/cyclone
Created: "2025-01-29  03:12:47"
Modified: 
Tags:
---

# fiorix/cyclone: Cyclone is a web server framework for Python, that implements the Tornado API as a Twisted protocol.

source: https://github.com/fiorix/cyclone

> ## Excerpt
> Cyclone is a web server framework for Python, that implements the Tornado API as a Twisted protocol. - fiorix/cyclone

---
## Cyclone

[![Build Status](https://camo.githubusercontent.com/ab30ae5b7204a9cf4585b9823f46b8f833eebd8feaafba5bb27d50691e531996/68747470733a2f2f7472617669732d63692e6f72672f66696f7269782f6379636c6f6e652e7376673f6272616e63683d6d6173746572)](https://travis-ci.org/fiorix/cyclone) [![Coverage Status](https://camo.githubusercontent.com/1f6c20e3baeb0007da4e7f7164985a86edfd3ded39648c689738a79f5dbf7260/68747470733a2f2f636f766572616c6c732e696f2f7265706f732f6769746875622f66696f7269782f6379636c6f6e652f62616467652e7376673f6272616e63683d6d6173746572)](https://coveralls.io/github/fiorix/cyclone?branch=master)

Cyclone is a web server framework for Python, that implements the Tornado API as a Twisted protocol.

⚠️ `cyclone` does not support `python` **2.x** anymore ⚠️

See [http://cyclone.io](http://cyclone.io/) for details.

## Installation

Cyclone is listed in PyPI and can be installed with pip or easy\_install. Note that the source distribution includes demo applications that are not present when Cyclone is installed in this way, so you may wish to download a copy of the source tarball as well.

## Manual installation

Download the latest release from [http://pypi.python.org/pypi/cyclone](http://pypi.python.org/pypi/cyclone)

```
tar zxvf cyclone-$VERSION.tar.gz
cd cyclone-$VERSION
sudo python setup.py install
```

The Cyclone source code is hosted on GitHub: [https://github.com/fiorix/cyclone](https://github.com/fiorix/cyclone)

## Prerequisites

Cyclone runs on Python 2.5, 2.6 and 2.7, and requires:

-   Twisted: [http://twistedmatrix.com/trac/wiki/Downloads](http://twistedmatrix.com/trac/wiki/Downloads)
-   pyOpenSSL: [https://launchpad.net/pyopenssl](https://launchpad.net/pyopenssl) (only if you want SSL/TLS)

On Python 2.5, simplejson is required too.

## Platforms

Cyclone should run on any Unix-like platform, although for the best performance and scalability only Linux and BSD (including BSD derivatives like Mac OS X) are recommended.

## Credits

Thanks to (in no particular order):

-   Nuswit Telephony API
    
    -   Granting permission for this code to be published and sponsoring
-   Gleicon Moraes
    
    -   Testing and using on RestMQ [https://github.com/gleicon/restmq](https://github.com/gleicon/restmq)
-   Vanderson Mota
    
    -   Patching setup.py and PyPi maintenance
-   Andrew Badr
    
    -   Fixing auth bugs and adding current Tornado's features
-   Jon Oberheide
    
    -   Syncing code with Tornado and security features/fixes
-   Silas Sewell [https://github.com/silas](https://github.com/silas)
    
    -   Syncing code and minor mail fix
-   Twitter Bootstrap [https://github.com/twitter/bootstrap](https://github.com/twitter/bootstrap)
    
    -   For making our demo applications look good
-   Dan Griffin [https://github.com/dgriff1](https://github.com/dgriff1)
    
    -   WebSocket Keep-Alive for OpDemand
-   Toby Padilla [https://github.com/tobypadilla](https://github.com/tobypadilla)
    
    -   WebSocket server
-   Jeethu Rao [https://github.com/jeethu](https://github.com/jeethu)
    
    -   Minor bugfixes and patches
-   Flavio Grossi [https://github.com/flaviogrossi](https://github.com/flaviogrossi)
    
    -   Minor code fixes and websockets chat statistics example
-   Gautam Jeyaraman [https://github.com/gautamjeyaraman](https://github.com/gautamjeyaraman)
    
    -   Minor code fixes and patches
-   DhilipSiva [https://github.com/dhilipsiva](https://github.com/dhilipsiva)
    
    -   Minor patches
