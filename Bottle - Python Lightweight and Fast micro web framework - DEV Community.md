---
Description: Bottle - Python Lightweight and Fast micro web framework - DEV Community
Notes: Bottle is a lightweight and fast micro web framework for Python. It is designed to be simple and easy...
author: 
Url: https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl
Created: "2025-01-29  03:07:19"
Modified: 
Tags:
---

# Bottle - Python Lightweight and Fast micro web framework - DEV Community

source: https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl

> ## Excerpt
> Bottle is a lightweight and fast micro web framework for Python. It is designed to be simple and easy...

---
Bottle is a lightweight and fast micro web framework for Python. It is designed to be simple and easy to use, making it ideal for small web applications, prototypes, or APIs.

Key Features:

1.  Single File Deployment: Bottle can run entirely from a single Python file without any dependencies other than the Python standard library. This makes it easy to deploy and maintain small projects.
    
2.  Built-in HTTP Server: It comes with a built-in server but can also be configured to run on other WSGI-compliant servers like Gunicorn or uWSGI.
    
3.  Routing: Bottle provides simple and powerful routing capabilities. It maps URLs to functions, which handle requests and return responses.
    
4.  Templates: It has a built-in templating engine, allowing you to create dynamic HTML content easily.
    
5.  Plugins: Bottle supports plugins, which are components that can be added to extend its functionality. Common plugins include support for databases like SQLite, MySQL, or MongoDB.
    
6.  WSGI Compliant: Bottle is fully WSGI-compliant, meaning it can be integrated with other WSGI-compatible applications and middleware.
    

___

1.  Installing Bottle

Before you can start using Bottle, you'll need to install it. Bottle is a pure Python package, and installation is straightforward:

pip install bottle

This installs the Bottle framework and makes it available for use in your projects.

1.  Creating a Simple Application

Here’s how you can create a basic web application using Bottle:

from bottle import Bottle, run

## [](https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl#create-an-instance-of-the-bottle-application)Create an instance of the Bottle application

app = Bottle()

## [](https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl#define-a-route-that-maps-to-a-url-path)Define a route that maps to a URL path

@app.route('/hello')  
def hello():  
return "Hello, World!"

## [](https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl#run-the-application-on-localhost-and-port-8080)Run the application on localhost and port 8080

run(app, host='localhost', port=8080)

Explanation:

Bottle() creates an application instance. This instance is used to define routes and handle requests.

@app.route('/hello') is a decorator that defines a route, mapping the URL /hello to the function hello(). Whenever this URL is accessed, the hello() function is called, and the string "Hello, World!" is returned as a response.

run(app, host='localhost', port=8080) starts the built-in web server, making your application accessible at [http://localhost:8080/hello](http://localhost:8080/hello).

1.  Running the Application

To run the example above, save the code to a file, say app.py, and execute it:

python app.py

Navigate to [http://localhost:8080/hello](http://localhost:8080/hello) in your browser, and you should see "Hello, World!" displayed.

1.  Key Terminologies

Understanding these core concepts will help you build more complex applications with Bottle:

4.1. Route

A route is a way to define how specific URLs should be handled by your application. Bottle uses decorators to map URLs to Python functions.

For example:

@app.route('/hello/')  
def greet(name):  
return f"Hello, {name}!"

Here, is a dynamic segment, which means if you visit [http://localhost:8080/hello/John](http://localhost:8080/hello/John), the output will be "Hello, John!".

4.2. Request and Response

Request: The request object contains information about the HTTP request received by the server, such as headers, query parameters, form data, etc.

from bottle import request

@app.route('/login', method='POST')  
def login():  
username = request.forms.get('username')  
password = request.forms.get('password')  
return f"Username: {username}, Password: {password}"

This example shows how to extract form data sent via a POST request.

Response: The function linked to a route can return a string (HTML), JSON, or other response objects. Bottle allows you to set headers, status codes, and more.

from bottle import response

@app.route('/json')  
def json\_example():  
response.content\_type = 'application/json'  
return '{"name": "John", "age": 30}'

4.3. Templates

Templates allow you to separate HTML content from the logic of your application. Bottle includes a basic template engine to make this easy:

from bottle import template

@app.route('/hello/')  
def hello(name):  
return template('**Hello {{name}}**!', name=name)

template() renders a template string, substituting the value of name.

You can also use external template files:

**Hello {{name}}**!

@app.route('/hello/')  
def hello(name):  
return template('hello', name=name)

4.4. Static Files

Bottle can serve static files such as CSS, JavaScript, or images during development:

from bottle import static\_file

@app.route('/static/')  
def serve\_static(filename):  
return static\_file(filename, root='/path/to/static/files')

Replace '/path/to/static/files' with the directory where your static files are stored.

4.5. Plugins

Bottle allows you to extend functionality using plugins. For example, you can integrate databases with your application easily using database plugins:

from bottle.ext import sqlite

## [](https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl#install-sqlite-plugin)Install SQLite plugin

app.install(sqlite.Plugin(dbfile='/path/to/database.db'))

4.6. Error Handling

You can create custom error pages using Bottle’s error handling capabilities:

@app.error(404)  
def error404(error):  
return 'Sorry, the page does not exist!'

4.7. Middleware

Bottle is WSGI-compliant, meaning you can use middleware to add functionality, such as logging, authentication, etc.

Example of simple middleware:

class SimpleMiddleware:  
def **init**(self, app):  
self.app = app

```
def __call__(self, environ, start_response):
    print("Middleware: Received request")
    return self.app(environ, start_response)
```

app = SimpleMiddleware(app)

1.  Building a Full Example Application

Let’s build an example that combines everything we’ve covered:

from bottle import Bottle, run, request, template, static\_file

app = Bottle()

## [](https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl#serve-the-homepage)Serve the homepage

@app.route('/')  
def home():  
return template('

Name: ')

## [](https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl#handle-form-submission)Handle form submission

@app.route('/greet', method='POST')  
def greet():  
name = request.forms.get('name')  
return template('Hello, {{name}}!', name=name)

## [](https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl#serve-static-files)Serve static files

@app.route('/static/')  
def serve\_static(filename):  
return static\_file(filename, root='./static')

## [](https://dev.to/mrcaption49/bottle-python-lightweight-and-fast-micro-web-framework-25bl#error-handling)Error handling

@app.error(404)  
def error404(error):  
return 'Page not found. Please check the URL.'

run(app, host='localhost', port=8080)

Explanation:

Homepage: Shows a form where the user can enter a name.

Greet Route: Processes the form input and displays a greeting.

Static Files: Demonstrates how to serve CSS, JS, or images.

Error Handling: Displays a custom 404 error message.

1.  Why Use Bottle?

Advantages:

Lightweight: Only a single file, no dependencies apart from the Python standard library.

Simple: Easy to learn and use, perfect for small projects or prototypes.

Extensible: Supports plugins and middleware, so it can grow with your project.

Use Cases:

Building APIs or microservices

Rapid prototyping

Small to medium-sized web applications

Embedding a web server in Python-based tools or scripts

Conclusion

Bottle is an excellent choice for developers looking to build small web applications quickly without much setup. Understanding how routes, templates, requests, and responses work will enable you to create effective and efficient applications. With the right plugins and middleware, you can expand Bottle’s functionality to fit more complex use cases.
