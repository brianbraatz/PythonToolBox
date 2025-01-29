---
Description: Mastering Python For Web Development. - DEV Community
Notes: How can an aspiring developer master Python for web development in today's world? Reading books,...
author: 
Url: https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3
Created: "2025-01-29  03:08:49"
Modified: 
Tags:
---

# Mastering Python For Web Development. - DEV Community

source: https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3

> ## Excerpt
> How can an aspiring developer master Python for web development in today's world? Reading books,...

---
How can an aspiring developer master Python for web development in today's world? Reading books, documents, blog posts or articles relating to the subject matter? Watching online tutorials? Attending class of web development physically? or Practicing everything that you learn on web development?  
Any learning technique that enables you to get the best out of yourself while learning is what any learner should prefer to use to become a master/great programmer.  
Python, being a practical language, it offers a concise and clear syntax which is easy to write and understand. Most developers and learners prefer Python for web development since it is a very powerful tool which has been used to back some of the world's most common products and services.  
Python offers many frameworks used in web developments such as _Django_, _Flask_, _Cherrypy_, _Pyramid_, _web2py_, and _Turbogears_ that has been used by power some of the most successful websites such as Google, Netflix, NASA and many more.   
In order to master Python for web development visit as many online learning platforms like [Cousera](http://www.cousera.org/), [Freecodecamp.org](http://www.freecodecamp.org/), [Udemy](http://www.udemy.com/), [Future learn](http://www.futurelearn.com/), [W3schools](http://www.w3schools.com/) and [IBM](http://www.ibm.com/) to be conversant with different Python coding information out there. In addition to that _Youtube_ tutorials on Python and other learning documentations of various frameworks will be helpful to you.  
In this article, I will discuss Mastering Python for web development using Django where I show you how to create and develop a web project and so much more.

### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#reasons-for-using-python-for-web-development)**Reasons for Using Python For Web Development.**

1.  Django is published under BSD license, which assures the web applications can be used and modified freely without experiencing problems. It is free and open source.
2.  Django integrates a lot of efficient ways to perform unit tests.
3.  Django is fully customizable, developers can adapt to it easily by creating modules or overridden framework methods.
4.  Uses the Don't Repeat Yourself (DRY) principle which keeps the code simple and clear without having to copy/paste the same code elsewhere.
5.  Using python in this framework allows you to have benefits from all Python libraries and assures a very good readability.
6.  Django is supported by a good community which means that you can easily resolve issues and fix bugs quickly as a result of many code examples that shows good practices.

### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#django-framework)**Django Framework**

**Django** is a high-level python web framework that allows rapid development and clean practical design which was released in 2005 and named after a jazz guitarist Django Reinhardt.  
It was first started in 2003 by Adrian Holovaty and Simon Willison as an internal project at Lawrence Journal-World newspaper and was released in July, 2005.  
Using Django it is easier to build a better web app faster and with less code plus its free and open source.

### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#features-of%C2%A0django)**Features of Django**

**Complete:** Strives to provide almost everything that developers require to help them develop their sites from consistent design patterns to extensive updated documentations.  
**Versatile:** Some organizations uses Django to build all sort of things from content management system to social networks to scientific computing platforms to new sites.  
**Secure:** Emphasizes on security by assisting developers to avoid many common mistakes by providing a framework to protect the website automatically. Also gives a secure way to manage user accounts and passwords.  
**Scalable:** Many of the busiest websites uses Django's ability to quickly and flexibly scale to meet the heaviest traffic demands.  
**Maintainable:** Applies design principles and patterns that encourage the creation of maintainable and reusable code. By making use of Don't Repeat Yourself (DRY) principle so there is no unnecessary duplication, reducing the amount of code.  
**Portable:** written in Python which runs on multiple platforms including Windows, Linux, Mac OS applications plus Django is well supported by many web-hosting providers that provides specific infrastructure and documentation for hosting Django sites.

### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#django-installation-process)**Django Installation Process**

In order to be able to use Django, you need to install the following Softwares:

-   Python
-   PIP which facilitates the installation of Django and other important packages
-   Django
-   Virtual environment

#### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#installation-of%C2%A0python)**Installation of Python**

Depending on the operating system, Windows, Unix/Linux and Mac OS Python can be installed on each operating system.  
For an elaborated step-by-step installing process of Python on your P.Cs make sure to check my article on [Ultimate Python Tutorial Guide For Beginners.](https://medium.com/@sleeksville-creations/python-101-the-ultimate-python-tutorial-for-beginners-c267b8f86f36) 

#### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#installation-of%C2%A0pip)**Installation of PIP**

**PIP** is important as it handles the packages installation, performs updates, and removes all the Python package extensions.

**Windows**  
Download it from [Here](https://pypi.org/project/pip/)  
Then you install PIP from executable and remember to choose the correct python installation folder.

**Unix/Linux**  
Run the following commands to be able to install PIP.  

```
<span>root</span><span>@sleekscreations</span><span>:</span> <span>wget</span> <span>https</span><span>:</span><span>//</span><span>raw</span><span>.</span><span>github</span><span>.</span><span>com</span><span>/</span><span>pypa</span><span>/</span><span>pip</span><span>/</span><span>master</span><span>/</span><span>contrib</span><span>/</span><span>get</span><span>-</span><span>pip</span><span>.</span><span>py</span>
<span>root</span><span>@sleekscreations</span><span>:</span> <span>python3</span> <span>get</span><span>-</span><span>pip</span><span>.</span><span>py</span>
```

**Mac OS**  
Open up your terminal and run the get-pip.py file as shown below.  

```
<span>$</span> <span>curl</span> <span>-</span><span>O</span> <span>https</span><span>:</span><span>//</span><span>raw</span><span>.</span><span>github</span><span>.</span><span>com</span><span>/</span><span>pypa</span><span>/</span><span>pip</span><span>/</span><span>master</span><span>/</span><span>contrib</span><span>/</span><span>get</span><span>-</span><span>pip</span><span>.</span><span>py</span>
<span>$</span> <span>sudo</span> <span>python3</span> <span>get</span><span>-</span><span>pip</span><span>.</span><span>py</span>
```

**Note that:**  
To confirm whether pip is installed in your P.C, open your terminal and run the command _pip --version_ or _pip3 --version._ If you get the pip version then it is safe to say that it has been installed.  

```
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>$</span> <span>pip</span> <span>--</span><span>version</span>
<span>pip</span> <span>20.3</span><span>.</span><span>4</span> <span>from</span><span>/</span><span>usr</span><span>/</span><span>lib</span><span>/</span><span>python3</span><span>/</span><span>dist</span><span>-</span><span>packages</span><span>/</span><span>pip </span><span>(</span><span>python</span> <span>3.9</span><span>)</span>
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>$</span> <span>pip3</span> <span>--</span><span>version</span>
<span>pip</span> <span>20.3</span><span>.</span><span>4</span> <span>from</span><span>/</span><span>usr</span><span>/</span><span>lib</span><span>/</span><span>python3</span><span>/</span><span>dist</span><span>-</span><span>packages</span><span>/</span><span>pip </span><span>(</span><span>python</span> <span>3.9</span><span>)</span>
```

In any case you are not getting any result after executing the above command or you did manage to install pip run the command sudo apt install pip or sudo apt install pip3 on your terminal

### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#installation-of%C2%A0django)**Installation of Django**

**Django for Windows**  
To install Django with PIP, open command prompt then go to Scripts directory where Python folder is and install Django by running the below command.  

```
<span>C</span><span>:</span>\<span>Python33</span>\<span>Scripts</span>\<span>pip</span><span>.</span><span>exe</span> <span>install</span> <span>django</span><span>==</span><span>"</span><span>X.X</span><span>"</span>
```

**Django for Linux**  
At the root level on your terminal execute the following codes.  

```
<span>root</span><span>@sleekscreations</span><span>:</span> <span>compgen</span> <span>-</span><span>c</span> <span>|</span> <span>grep</span> <span>pip</span>
<span>root</span><span>@sleekscreations</span><span>:</span> <span>alias</span> <span>pip</span><span>=</span><span>pip</span><span>-</span><span>3.2</span>
<span>root</span><span>@sleekscreations</span><span>:</span> <span>pip</span> <span>install</span> <span>django</span><span>==</span><span>"</span><span>1.6</span><span>"</span>
```

**Django for Mac OS**  
We install Django by running the command _pip install django=="1.6"_ on the terminal.  

```
<span>$</span> <span>cd</span> <span>usr</span><span>/</span><span>local</span><span>/</span><span>bin</span>
<span>ln</span> <span>-</span><span>s</span> <span>..</span><span>/</span><span>..</span><span>/</span><span>..</span><span>/</span><span>Library</span><span>/</span><span>Frameworks</span><span>/</span><span>Python</span><span>.</span><span>framework</span><span>/</span><span>Version</span><span>/</span><span>3.3</span><span>/</span><span>bin</span><span>/</span><span>pip3</span>
<span>pip</span>
<span>$</span> <span>pip</span> <span>install</span> <span>django</span><span>==</span><span>"</span><span>1.6</span><span>"</span>
```

### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#installing-virtual-environmentvirtualenv)**Installing Virtual Environment(Virtualenv)**

We are creating a virtual environment to have a separate working environment for our new project.  
In order to install virtualenv, lets run _pip_ or _pip3_ then using PIP we run _pip install virtualenv._  
To check if virtualenv is installed the run the command _virtualenv--version._  

```
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>$</span> <span>virtualenv</span><span>--</span><span>version</span>
<span>virtualenv</span> <span>20.10</span><span>.</span><span>0</span>
```

### [](https://dev.to/sleekscreatess/mastering-python-for-web-development-5hj3#creating-our-first-project-with%C2%A0django)**Creating Our First Project with Django**

-   Before we start to use Django, lets create a folder/directory for this project on the Desktop by running the following command on the terminal.

```
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>$</span> <span>pwd</span>
<span>user</span><span>/</span><span>home</span><span>/</span><span>sleekscreations</span>
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>$</span> <span>ls</span>
<span>Desktop</span> <span>Documents</span> <span>Downloads</span> <span>Pictures</span> <span>Music</span> 
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>$</span> <span>cd</span> <span>Desktop</span><span>/</span>
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span> <span>$</span> <span>mkdir</span> <span>demo_django</span>
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span> <span>$</span> <span>ls</span>
<span>demo_django</span>
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span> <span>$</span> <span>cd</span> <span>demo_django</span>
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span>
```

-   Under our new directory, lets create virtual environment by using the command _virtualenv_

```
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>virtualenv</span> <span>env</span>
```

-   Make sure you activate the environment using _source /bin/activate_.

```
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>source</span> <span>env</span><span>/</span><span>bin</span><span>/</span><span>activate</span>
```

-   Inside our same created directory lets install Django by running _pip install django_.

```
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>pip</span> <span>install</span> <span>django</span>
<span>Collecting</span> <span>django</span>
  <span>Using</span> <span>cached</span> <span>Django</span><span>-</span><span>4.0</span><span>.</span><span>2</span><span>-</span><span>py3</span><span>-</span><span>none</span><span>-</span><span>any</span><span>.</span><span>whl </span><span>(</span><span>8.0</span> <span>MB</span><span>)</span>
<span>Collecting</span> <span>sqlparse</span><span>&gt;=</span><span>0.2</span><span>.</span><span>2</span>
  <span>Using</span> <span>cached</span> <span>sqlparse</span><span>-</span><span>0.4</span><span>.</span><span>2</span><span>-</span><span>py3</span><span>-</span><span>none</span><span>-</span><span>any</span><span>.</span><span>whl </span><span>(</span><span>42</span> <span>kB</span><span>)</span>
<span>Collecting</span> <span>asgiref</span><span>&lt;</span><span>4</span><span>,</span><span>&gt;=</span><span>3.4</span><span>.</span><span>1</span>
  <span>Using</span> <span>cached</span> <span>asgiref</span><span>-</span><span>3.5</span><span>.</span><span>0</span><span>-</span><span>py3</span><span>-</span><span>none</span><span>-</span><span>any</span><span>.</span><span>whl </span><span>(</span><span>22</span> <span>kB</span><span>)</span>
<span>Installing</span> <span>collected</span> <span>packages</span><span>:</span> <span>sqlparse</span><span>,</span> <span>asgiref</span><span>,</span> <span>django</span>
<span>Successfully</span> <span>installed</span> <span>asgiref</span><span>-</span><span>3.5</span><span>.</span><span>0</span> <span>django</span><span>-</span><span>4.0</span><span>.</span><span>2</span> <span>sqlparse</span><span>-</span><span>0.4</span><span>.</span><span>2</span>
```

-   Lets begin our project by running the command _django-admin startproject django\_project1_ which will create our project files on **django\_project1** and **manage.py** file.

```
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>django</span><span>-</span><span>admin</span> <span>startproject</span> <span>django_project1</span>
<span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>ls</span>
<span>django_project1</span> <span>env</span> <span>manage</span><span>.</span><span>py</span>
```

-   Now let make columns and tables in the database using the migration and migrate commands _./manage.py makemigrations_ and then _./manage.py migrate._

```
<span>[</span><span>env</span><span>]</span> <span>-</span> <span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>.</span><span>/</span><span>manage</span><span>.</span><span>py</span> <span>makemigrations</span>
<span>[</span><span>env</span><span>]</span> <span>-</span> <span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>.</span><span>/</span><span>manage</span><span>.</span><span>py</span> <span>migrate</span>   <span>#copy all migrations to the database
</span><span>Operations</span> <span>to</span> <span>perform</span><span>:</span>
  <span>Apply</span> <span>all</span> <span>migrations</span><span>:</span> <span>admin</span><span>,</span> <span>auth</span><span>,</span> <span>contenttypes</span><span>,</span> <span>sessions</span>
<span>Running</span> <span>migrations</span><span>:</span>
  <span>Applying</span> <span>contenttypes</span><span>.</span><span>0001</span><span>_initial</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0001</span><span>_initial</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>admin</span><span>.</span><span>0001</span><span>_initial</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>admin</span><span>.</span><span>0002</span><span>_logentry_remove_auto_add</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>admin</span><span>.</span><span>0003</span><span>_logentry_add_action_flag_choices</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>contenttypes</span><span>.</span><span>0002</span><span>_remove_content_type_name</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0002</span><span>_alter_permission_name_max_length</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0003</span><span>_alter_user_email_max_length</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0004</span><span>_alter_user_username_opts</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0005</span><span>_alter_user_last_login_null</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0006</span><span>_require_contenttypes_0002</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0007</span><span>_alter_validators_add_error_messages</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0008</span><span>_alter_user_username_max_length</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0009</span><span>_alter_user_last_name_max_length</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0010</span><span>_alter_group_name_max_length</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0011</span><span>_update_proxy_permissions</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>auth</span><span>.</span><span>0012</span><span>_alter_user_first_name_max_length</span><span>...</span> <span>OK</span>
  <span>Applying</span> <span>sessions</span><span>.</span><span>0001</span><span>_initial</span><span>...</span> <span>OK</span>
```

-   Consequently, as we are working on the project's main container directory on the manage.py file lets run _./manage.py runserver_ which runs on port **8000** by default but if we specify the port number it won't run on default e.g _./manage.py runserver 7000_

```
<span>[</span><span>env</span><span>]</span> <span>-</span> <span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>.</span><span>/</span><span>manage</span><span>.</span><span>py</span> <span>runserver</span>
<span>Performing</span> <span>system</span> <span>checks</span><span>...</span>

<span>System</span> <span>check</span> <span>identified</span> <span>no</span> <span>issues </span><span>(</span><span>0</span> <span>silenced</span><span>).</span>
<span>May</span> <span>1</span><span>,</span> <span>2022</span> <span>-</span> <span>10</span><span>:</span><span>51</span><span>:</span><span>11</span>
<span>Django</span> <span>version</span> <span>4.0</span><span>.</span><span>2</span><span>,</span> <span>using</span> <span>settings</span> <span>'</span><span>django_project1.settings</span><span>'</span>
<span>Starting</span> <span>development</span> <span>server</span> <span>at</span> <span>http</span><span>:</span><span>//</span><span>127.0</span><span>.</span><span>0.1</span><span>:</span><span>8000</span><span>/</span>
<span>Quit</span> <span>the</span> <span>server</span> <span>with</span> <span>CONTROL</span><span>-</span><span>C</span><span>.</span>
```

Next, visit **[https://127.0.0.1:8000/](https://127.0.0.1:8000/)** which will display the page shown below.

[![Image description](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fihge7o6ue02t1dqoea8l.png)](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fihge7o6ue02t1dqoea8l.png)

**Another method is by running the server on a shared IP address to enable people within the network to be able to view your project.**

-   Lets run _ifconfig_ to check ip and interphase.

```
<span>[</span><span>env</span><span>]</span> <span>-</span> <span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>ifconfig</span>
<span>eth0</span><span>:</span> <span>flags</span><span>=</span><span>4099</span><span>&lt;</span><span>UP</span><span>,</span><span>BROADCAST</span><span>,</span><span>MULTICAST</span><span>&gt;</span>  <span>mtu</span> <span>1500</span>
        <span>ether</span> <span>d8</span><span>:</span><span>9</span><span>d</span><span>:</span><span>67</span><span>:</span><span>cb</span><span>:</span><span>cf</span><span>:</span><span>96</span>  <span>txqueuelen</span> <span>1000</span>  <span>(</span><span>Ethernet</span><span>)</span>
        <span>RX</span> <span>packets</span> <span>0</span>  <span>bytes</span> <span>0</span> <span>(</span><span>0.0</span> <span>B</span><span>)</span>
        <span>RX</span> <span>errors</span> <span>0</span>  <span>dropped</span> <span>0</span>  <span>overruns</span> <span>0</span>  <span>frame</span> <span>0</span>
        <span>TX</span> <span>packets</span> <span>0</span>  <span>bytes</span> <span>0</span> <span>(</span><span>0.0</span> <span>B</span><span>)</span>
        <span>TX</span> <span>errors</span> <span>0</span>  <span>dropped</span> <span>0</span> <span>overruns</span> <span>0</span>  <span>carrier</span> <span>0</span>  <span>collisions</span> <span>0</span>

<span>lo</span><span>:</span> <span>flags</span><span>=</span><span>73</span><span>&lt;</span><span>UP</span><span>,</span><span>LOOPBACK</span><span>,</span><span>RUNNING</span><span>&gt;</span>  <span>mtu</span> <span>65536</span>
        <span>inet</span> <span>127.0</span><span>.</span><span>0.1</span>  <span>netmask</span> <span>255.0</span><span>.</span><span>0.0</span>
        <span>inet6</span> <span>::</span><span>1</span>  <span>prefixlen</span> <span>128</span>  <span>scopeid</span> <span>0x10</span><span>&lt;</span><span>host</span><span>&gt;</span>
        <span>loop</span>  <span>txqueuelen</span> <span>1000</span>  <span>(</span><span>Local</span> <span>Loopback</span><span>)</span>
        <span>RX</span> <span>packets</span> <span>17931</span>  <span>bytes</span> <span>4982556</span> <span>(</span><span>4.7</span> <span>MiB</span><span>)</span>
        <span>RX</span> <span>errors</span> <span>0</span>  <span>dropped</span> <span>0</span>  <span>overruns</span> <span>0</span>  <span>frame</span> <span>0</span>
        <span>TX</span> <span>packets</span> <span>17931</span>  <span>bytes</span> <span>4982556</span> <span>(</span><span>4.7</span> <span>MiB</span><span>)</span>
        <span>TX</span> <span>errors</span> <span>0</span>  <span>dropped</span> <span>0</span> <span>overruns</span> <span>0</span>  <span>carrier</span> <span>0</span>  <span>collisions</span> <span>0</span>

<span>usb0</span><span>:</span> <span>flags</span><span>=</span><span>4163</span><span>&lt;</span><span>UP</span><span>,</span><span>BROADCAST</span><span>,</span><span>RUNNING</span><span>,</span><span>MULTICAST</span><span>&gt;</span>  <span>mtu</span> <span>1500</span>
        <span>inet</span> <span>192.168</span><span>.</span><span>42.220</span>  <span>netmask</span> <span>255.255</span><span>.</span><span>255.0</span>  <span>broadcast</span> <span>192.168</span><span>.</span><span>42.255</span>
        <span>inet6</span> <span>fe80</span><span>::</span><span>70</span><span>d8</span><span>:</span><span>a7f</span><span>:</span><span>4</span><span>daf</span><span>:</span><span>43</span><span>f7</span>  <span>prefixlen</span> <span>64</span>  <span>scopeid</span> <span>0x20</span><span>&lt;</span><span>link</span><span>&gt;</span>
        <span>ether</span> <span>2</span><span>a</span><span>:</span><span>52</span><span>:</span><span>c0</span><span>:</span><span>42</span><span>:</span><span>23</span><span>:</span><span>3</span><span>b</span>  <span>txqueuelen</span> <span>1000</span>  <span>(</span><span>Ethernet</span><span>)</span>
        <span>RX</span> <span>packets</span> <span>764</span>  <span>bytes</span> <span>205457</span> <span>(</span><span>200.6</span> <span>KiB</span><span>)</span>
        <span>RX</span> <span>errors</span> <span>0</span>  <span>dropped</span> <span>0</span>  <span>overruns</span> <span>0</span>  <span>frame</span> <span>0</span>
        <span>TX</span> <span>packets</span> <span>828</span>  <span>bytes</span> <span>165938</span> <span>(</span><span>162.0</span> <span>KiB</span><span>)</span>
        <span>TX</span> <span>errors</span> <span>0</span>  <span>dropped</span> <span>0</span> <span>overruns</span> <span>0</span>  <span>carrier</span> <span>0</span>  <span>collisions</span> <span>0</span>
```

-   In our case here we will have to copy the IP address **192.168.42.255** on the same interphase usb0.
-   Now using _manage.py runserver :_
-   Lets run _./manage.py runserver 192.168.42.220.80_

```
<span>[</span><span>env</span><span>]</span> <span>-</span> <span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span> <span>.</span><span>/</span><span>manage</span><span>.</span><span>py</span> <span>runserver</span> <span>192.168</span><span>.</span><span>42.220</span><span>:</span><span>80</span>                                 
<span>Watching</span> <span>for</span> <span>file</span> <span>changes</span> <span>with</span> <span>StatReloader</span>
<span>Performing</span> <span>system</span> <span>checks</span><span>...</span>

<span>System</span> <span>check</span> <span>identified</span> <span>no</span> <span>issues </span><span>(</span><span>0</span> <span>silenced</span><span>).</span>
<span>February</span> <span>10</span><span>,</span> <span>2022</span> <span>-</span> <span>05</span><span>:</span><span>07</span><span>:</span><span>08</span>
<span>Django</span> <span>version</span> <span>4.0</span><span>.</span><span>2</span><span>,</span> <span>using</span> <span>settings</span> <span>'</span><span>Django_Project.settings</span><span>'</span>
<span>Starting</span> <span>development</span> <span>server</span> <span>at</span> <span>http</span><span>:</span><span>//</span><span>192.168</span><span>.</span><span>42.220</span><span>:</span><span>80</span><span>/</span>
<span>Quit</span> <span>the</span> <span>server</span> <span>with</span> <span>CONTROL</span><span>-</span><span>C</span><span>.</span>
```

-   On the terminal to create a superuser run _Python3 manage.py createsuperuser_ or _./manage.py createsuperuser_ and fill in the name the user, give an email, and set a password. Now, running your server _./manage.py runserver_ it will allow you to access the Django admin panel for your project.

```
<span>[</span><span>env</span><span>]</span> <span>-</span> <span>sleekscreations</span><span>@sleekscreations</span><span>:</span><span>~</span> <span>Desktop</span><span>/</span><span>demo_django</span> <span>$</span>
<span>.</span><span>/</span><span>manage</span><span>.</span><span>py</span> <span>createsuperuser</span>                                             
<span>Username </span><span>(</span><span>leave</span> <span>blank</span> <span>to</span> <span>use</span> <span>'</span><span>Sleekscreations</span><span>'</span><span>):</span> <span>admin</span>
<span>Email</span> <span>address</span><span>:</span> <span>admin</span><span>.</span><span>admin</span><span>@outlook.com</span>
<span>Password</span><span>:</span> 
<span>Password </span><span>(</span><span>again</span><span>):</span> 
<span>Superuser</span> <span>created</span> <span>successfully</span><span>.</span>
```

-   Now try visit **[https://127.0.0.1:8000/admin](https://127.0.0.1:8000/admin)** to check if you can be able to log in on the login admin page.

**Login page for Admin**  
Fill out your details on the page i.e., the username and password that we created earlier:

[![Image description](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fs7nmlszlkuy2tpa99f7e.png)](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fs7nmlszlkuy2tpa99f7e.png)

**Admin page:**  
View your admin panel afterward on the page below.

[![Image description](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Ft3ymvq8bt4dj58uosr8i.png)](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Ft3ymvq8bt4dj58uosr8i.png)

For more information to master Django for web development check out:

-   [Creating a Django Web App](https://docs.djangoproject.com/en/4.0/intro/tutorial01/)
-   [Django Web development with Python](https://pythonprogramming.net/django-web-development-with-python-intro/)
-   [Learn Django Python Web Framework](https://www.tutorialspoint.com/django/index.htm)
