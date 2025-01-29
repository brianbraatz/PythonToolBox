---
Description: Quick start! getting started with flask, python3. - DEV Community
Notes: Python is a cool and beautiful programing language. It is beginner friendly, easy to learn and its...
author: 
Url: https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp
Created: "2025-01-29  03:13:47"
Modified: 
Tags:
---

# Quick start! getting started with flask, python3. - DEV Community

source: https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp

> ## Excerpt
> Python is a cool and beautiful programing language. It is beginner friendly, easy to learn and its...

---
Python is a cool and beautiful programing language. It is beginner friendly, easy to learn and its syntax is very clear and concise. Python is yet powerful enough to be used by global tech giants in their products and applications. One area where Python shines is web development. Python offers many frameworks from which to choose from including bottle.py, Flask, Fast API, CherryPy, Pyramid, Django and web2py. This frameworks have been used is some of the most world applications.

## [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#what-is-flask)What is flask.

Flask is a micro web framework written in Python. It is classified as a microframework because it does not require particular tools or libraries. It has no database abstraction layer, form validation, or any other components where pre-existing third-party libraries provide common functions. However, Flask supports extensions that can add application features as if they were implemented in Flask itself. Extensions exist for object-relational mappers, form validation, upload handling, various open authentication technologies and several common framework related tools.

## [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#setting-up-flask)Setting up Flask.

#### [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#python-virtual-environment)Python Virtual environment.

A virtual environment is a Python environment such that the Python interpreter, libraries and scripts installed into it are isolated from those installed in other virtual environments, and (by default) any libraries installed in a “system” Python, i.e., one which is installed as part of your operating system.  
virtual environment is used to manage Python packages for different projects. Using virtual environment allows you to avoid installing Python packages globally which could break system tools or other projects.

### [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#you-can-install-virtual-environment-using-pip-use-this-code-in-windows-i-recommend-using-git-bash-than-the-windows-cmd)You can install virtual environment using pip. Use this code in windows (I recommend using git bash than the windows CMD):

### [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#create-the-virtual-environment)Create the virtual environment.

my\_env is the name of the virtual environment we have created.

### [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#activate-the-virtual-environment)Activate the virtual environment.

```
<span>source</span> <span>my_env</span>\<span>Scripts</span>\<span>activate</span>
```

Now we have a virtual environment let install flask.

## [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#installing-flask)Installing flask.

Flask is easy to set up. Use pip install flask to install both Flask and all of its dependencies including the Jinja2 templating system.  

## [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#a-basic-flask-app)A basic Flask app.

```
<span>from</span> <span>flask</span> <span>import</span> <span>Flask</span>

<span>app</span> <span>=</span> <span>Flask</span><span>(</span><span>__name__</span><span>)</span>

<span>@</span><span>app</span><span>.</span><span>route</span><span>(</span><span>"/"</span><span>)</span>
<span>def</span> <span>hello_world</span><span>(</span><span>self</span><span>):</span>
    <span>return</span> <span>"Hello, world"</span>
```

This app doesn’t do much — it just creates a website with a single route that displays “Hello, world” in the browser.

## [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#routes-in-flask)Routes in flask.

Routes in a Flask app can be created by defining a view function and associating a URL with it using the route() decorator. Routes specify how the Flask app handles requests it receives, such as what to display on the webpage at a certain URL.  

```
<span>@</span><span>app</span><span>.</span><span>route</span><span>(</span><span>"/"</span><span>)</span>
<span>def</span> <span>hello_world</span><span>(</span><span>self</span><span>):</span>
    <span>return</span> <span>"Hello, world"</span>
```

## [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#flask-app-object)Flask App Object.

The Python flask module contains all the classes and functions needed for building a Flask app. The Flask class can be imported to create the main application object. It takes the name of the app as an argument.  

```
<span>from</span> <span>flask</span> <span>import</span> <span>Flask</span>

<span>app</span> <span>=</span> <span>Flask</span><span>(</span><span>__name__</span><span>)</span>
```

## [](https://dev.to/chris_murimi/quick-start-getting-started-with-flask-python3-40lp#running-flask-app)Running Flask App.

A Flask app can be run by exporting the FLASK\_APP environment variable and running flask run in the terminal.  

```
<span>export</span> <span>FLASK_APP</span><span>=</span><span>app</span><span>.</span><span>py</span>
<span>flask</span> <span>run</span> 
```
