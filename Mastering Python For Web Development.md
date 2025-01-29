---
Description: Mastering Python For Web Development. - DEV Community
Notes: Python, is a practical language, and so practice is the major key for any aspiring developer to excel...
author: 
Url: https://dev.to/mukumbuta/mastering-python-for-web-development-5bad
Created: "2025-01-29  03:08:30"
Modified: 
Tags:
---

# Mastering Python For Web Development. - DEV Community

source: https://dev.to/mukumbuta/mastering-python-for-web-development-5bad

> ## Excerpt
> Python, is a practical language, and so practice is the major key for any aspiring developer to excel...

---
Python, is a practical language, and so practice is the major key for any aspiring developer to excel at programming in python. Python offers a concise and clear syntax which is easy to write and understand. Most developers and learners prefer Python for web development since it is a very powerful tool which has been used to back some of the world's most common products and services. Python offers many frameworks used in web developments such as Django, Flask, Cherrypy, Pyramid, that has been used to power some of the most successful websites such as Google, Netflix, NASA and many more.

**Why Use Python For Web Development.**

1.  Django is published under BSD license, which assures the web applications can be used and modified freely without experiencing problems. It is free and open source.
2.  Django integrates a lot of efficient ways to perform unit tests.
3.  Django is fully customizable, developers can adapt to it easily by creating modules or overridden framework methods.
4.  Uses the Don't Repeat Yourself (DRY) principle which keeps the code simple and clear without having to copy/paste the same code elsewhere.
5.  Using python in this framework allows you to have benefits from all Python libraries and assures a very good readability.
6.  Django is supported by a good community which means that you can easily resolve issues and fix bugs quickly as a result of many code examples that shows good practices. Django Framework Django is a high-level python web framework that allows rapid development and clean practical design which was released in 2005 and named after a jazz guitarist Django Reinhardt. It was first started in 2003 by Adrian Holovaty and Simon Willison as an internal project at Lawrence Journal-World newspaper and was released in July, 2005. Using Django it is easier to build a better web app faster and with less code plus its free and open source. **Some of the Features of Django**

**Complete**: Strives to provide almost everything that developers require to help them develop their sites from consistent design patterns to extensive updated documentations.

**Versatile**: Some organizations uses Django to build all sort of things from content management system to social networks to scientific computing platforms to new sites.

**Secure**: Emphasizes on security by assisting developers to avoid many common mistakes by providing a framework to protect the website automatically. Also gives a secure way to manage user accounts and passwords.  
**Scalable**: Many of the busiest websites uses Django's ability to quickly and flexibly scale to meet the heaviest traffic demands.  
**Maintainable**: Applies design principles and patterns that encourage the creation of maintainable and reusable code. By making use of Don't Repeat Yourself (DRY) principle so there is no unnecessary duplication, reducing the amount of code.  
**Portable**: written in Python which runs on multiple platforms including Windows, Linux, Mac OS applications plus Django is well supported by many web-hosting providers that provides specific infrastructure and documentation for hosting Django sites.  
**Django Installation Process**  
In order to be able to use Django, you need to install the following Software:  
• Python  
• PIP which facilitates the installation of Django and other important packages  
• Django  
• Virtual environment  
Installation of Python  
Depending on the operating system, Windows, Unix/Linux and Mac OS Python can be installed on each operating system.

**Install PIP**  
PIP is important as it handles the packages installation, performs updates, and removes all the Python package extensions.  
Windows Download it from Here Then you install PIP from executable and remember to choose the correct python installation folder.  
Unix/Linux Run the following commands to be able to install PIP.  
root: wget [https://raw.github.com/pypa/pip/master/contrib/get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py)  
root: python3 get-pip.py  
Mac OS Open up your terminal and run the get-pip.py file as shown below.  
$ curl -O [https://raw.github.com/pypa/pip/master/contrib/get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py)  
$ sudo python3 get-pip.py  
Note that: To confirm whether pip is installed in your P.C, open your terminal and run the command pip --version or pip3 --version. If you get the pip version then it is safe to say that it has been installed.  
:~ $ pip --version  
pip 20.3.4 from/usr/lib/python3/dist-packages/pip (python 3.9)  
:~ $ pip3 --version  
pip 20.3.4 from/usr/lib/python3/dist-packages/pip (python 3.9)  
In any case you are not getting any result after executing the above command or you did manage to install pip run the command sudo apt install pip or sudo apt install pip3 on your terminal  
Installation of Django  
Django for Windows To install Django with PIP, open command prompt then go to Scripts directory where Python folder is and install Django by running the below command.  
C:\\Python33\\Scripts\\pip.exe install django=="X.X"  
Django for Linux At the root level on your terminal execute the following codes.  
root: compgen -c | grep pip  
root: alias pip=pip-3.2  
: pip install django=="1.6"  
Django for Mac OS We install Django by running the command pip install django=="1.6" on the terminal.  
$ cd usr/local/bin  
ln -s ../../../Library/Frameworks/Python.framework/Version/3.3/bin/pip3  
pip  
$ pip install django=="1.6"  
Installing Virtual Environment(Virtualenv)  
We are creating a virtual environment to have a separate working environment for our new project. In order to install virtualenv, lets run pip or pip3 then using PIP we run pip install virtualenv. To check if virtualenv is installed the run the command virtualenv--version.  
:~ $ virtualenv--version  
virtualenv 20.10.0  
Creating Our First Project with Django  
• Before we start to use Django, lets create a folder/directory for this project on the Desktop by running the following command on the terminal.  
:~ $ pwd  
user/home/muks  
:~ $ ls  
Desktop Documents Downloads Pictures Music  
:~ $ cd Desktop/  
:~ Desktop $ mkdir demo\_django  
:~ Desktop $ ls  
demo\_django  
:~ Desktop $ cd demo\_django  
~ Desktop/demo\_django $  
• Under our new directory, lets create virtual environment by using the command virtualenv  
~ Desktop/demo\_django $ virtualenv env  
• Make sure you activate the environment using source /bin/activate.  
:~ Desktop/demo\_django $ source env/bin/activate  
• Inside our same created directory lets install Django by running pip install django.  
:~ Desktop/demo\_django $ pip install django  
Collecting django  
• Lets begin our project by running the command django-admin startproject django\_project1 which will create our project files on django\_project1 and manage.py file.  
:~ Desktop/demo\_django $ django-admin startproject django\_project1  
:~ Desktop/demo\_django $ ls django\_project1 env manage.py  
• Now let make columns and tables in the database using the migration and migrate commands ./manage.py makemigrations and then ./manage.py migrate.

\[env\] ~ Desktop/demo\_django $ ./manage.py makemigrations  
• Consequently, as we are working on the project's main container directory on the manage.py file lets run ./manage.py runserver which runs on port 8000 by default but if we specify the port number it won't run on default e.g ./manage.py runserver 7000  
\[env\] :~ Desktop/demo\_django $ ./manage.py runserver  
Performing system checks...

System check identified no issues (0 silenced).  
May 1, 2022 - 10:51:11  
Django version 4.0.2, using settings 'django\_project1.settings'  
Starting development server at [http://127.0.0.1:8000/](http://127.0.0.1:8000/)  
Quit the server with CONTROL-C.  
Next, visit [https://127.0.0.1:8000/](https://127.0.0.1:8000/) which will display the page shown below.

• On the terminal to create a superuser run Python3 manage.py createsuperuser or ./manage.py createsuperuser and fill in the name the user, give an email, and set a password. Now, running your server ./manage.py runserver it will allow you to access the Django admin panel for your project.

\[env\]:~ Desktop/demo\_django $./manage.py createsuperuser

Username : admin  
Email address: [admin.admin@email.com](mailto:admin.admin@email.com)  
Password:  
Password (again):  
Superuser created successfully.  
• Now try visit [https://127.0.0.1:8000/admin](https://127.0.0.1:8000/admin) to check if you can be able to log in on the login admin page.  
Login page for Admin Fill out your details on the page i.e., the username and password that we created earlier:

Admin page: You can then view and explore your admin panel
