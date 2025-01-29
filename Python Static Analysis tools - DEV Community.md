---
Description: Python Static Analysis tools - DEV Community
Notes: In a survey by stack-overflow in 2020, developers worldwide ranked Python as the third most loved...
author: 
Url: https://dev.to/camelcaseguy/python-static-analysis-tools-275b
Created: "2025-01-29  03:11:18"
Modified: 
Tags:
---

# Python Static Analysis tools - DEV Community

source: https://dev.to/camelcaseguy/python-static-analysis-tools-275b

> ## Excerpt
> In a survey by stack-overflow in 2020, developers worldwide ranked Python as the third most loved...

---
In a survey by stack-overflow in 2020, developers worldwide ranked Python as the [third most loved programming language](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-languages-loved) and the topmost wanted programming language. Python is so popular among developers that no wonder why there are so many static analysis tools for it. But how do you choose the best static code analysis tool among them? In this blog, I'll share what, why, and how of static code analysis for your Python code.

### [](https://dev.to/camelcaseguy/python-static-analysis-tools-275b#what-is-static-code-analysis)**What is Static code analysis?**

Static code analysis is the process of analyzing a computer program to find problems in it without actually executing it. Generally, static analysis is performed on the source code of the program with tools that convert the program into an [abstract syntax tree (AST)](https://deepsource.io/glossary/ast/) to understand the code's structure and then find problems in it.

### [](https://dev.to/camelcaseguy/python-static-analysis-tools-275b#why-should-i-use-a-static-analysis-tool)**Why should I use a static analysis tool?**

Static code analysis can help identify the anti-patterns in the code and detect possible code quality and security issues. It lets you find and rectify issues in code at the early stages of development, reducing the chances of issues being raised later in the production. The type of static analysis done by these tools are:

-   Code styling analysis
-   Security linting
-   Error detection
-   UML diagram creation
-   Duplicate code detection
-   Complexity analysis
-   Comment styling analysis
-   Unused code detection

### [](https://dev.to/camelcaseguy/python-static-analysis-tools-275b#benefits-of-static-code-analysis)**Benefits of Static Code Analysis**

Static code analysis is not 100% accurate and sometimes returns false positives or false negatives. However, it has numerous benefits, including:

-   Relative accuracy - catch many more errors than by manual analysis
-   Speed to discover errors
-   Comprehensiveness of testing
-   Decreases risk of high impact error after software release
-   Ability to uncover errors that aren't usually detected during dynamic testing

### [](https://dev.to/camelcaseguy/python-static-analysis-tools-275b#top-static-analysis-tools-for-python)**Top static analysis tools for Python**

Let's take a look at the tools that exist in the Python ecosystem for static code analysis:

**[Pylint](https://pylint.org/)**

`pylint` is a static code analysis tool that lists error which may come after execution of the python code, helps to enforce a coding standard, and look for code smells, offers simple refactoring suggestions, and other suggestions about code complexity.

`pylint` has been around for 13 years, and it is still constantly maintained. Though it is pedantic out of the box, it is fully customizable through a `.pylintrc` file that you can customize for errors or agreements relevant to you.

**Example:**

Here is a program having some styling issues:

sample.py

```


<span>a</span> <span>=</span> <span>23</span>
<span>b</span> <span>=</span> <span>45</span>
<span>c</span> <span>=</span> <span>a</span> <span>+</span> <span>b</span>

<span>print</span><span>(</span><span>c</span><span>)</span>


```

After running `pylint` you'll get the following output that lists down multiple styling issues in the program.

```



% pylint sample.py  
<span>*************</span> Module sample
sample.py:5:0: C0304: Final newline missing <span>(</span>missing-final-newline<span>)</span>
sample.py:1:0: C0114: Missing module docstring <span>(</span>missing-module-docstring<span>)</span>
sample.py:1:0: C0103: Constant name <span>"a"</span> doesn<span>'t conform to UPPER_CASE naming style (invalid-name)
sample.py:2:0: C0103: Constant name "b" doesn'</span>t conform to UPPER_CASE naming style <span>(</span>invalid-name<span>)</span>
sample.py:3:0: C0103: Constant name <span>"c"</span> doesn<span>'t conform to UPPER_CASE naming style (invalid-name)



</span>
```

**[Pyflakes](https://github.com/PyCQA/pyflakes)**

`pyflakes` is a verification tool for python source code. It just doesn't verify the style at all but verifies only logistic errors. It emits very few false positives, which means that it will not display errors about missing docstrings or argument names that don't match the naming style.

What makes `pyflakes` faster than `pylint` is its ability to examine the AST of each file individually, combined with a limited set of errors.

You can install `pyflakes` with

```


<span>$ </span>pip <span>install</span> <span>--upgrade</span> pyflakes


```

As I mentioned before, `pyflakes` don’t do any stylistic checks, but if you want, you can do style checks using another tool called `Flake8` that combines `pyflakes` with `PEP8` style checks. Additionally, `Flake8` also gives you the advantage of adding configuration options for each project.

**[Mypy](http://mypy-lang.org/)**

`mypy` is slightly different from `pylint` and `pyflakes` as it is a static type checker for Python. It requires your code to be annotated using Python 3 function annotation syntax ([PEP484](https://www.python.org/dev/peps/pep-0484/)) in order to type-check the code and detect common bugs. The purpose of `mypy` is to combine the advantages of dynamic and static typing (using a typing module).

From Python...

```


<span>def</span> <span>fib</span><span>(</span><span>n</span><span>):</span>
    <span>a</span><span>,</span> <span>b</span> <span>=</span> <span>0</span><span>,</span> <span>1</span>
    <span>while</span> <span>a</span> <span>&lt;</span> <span>n</span><span>:</span>
        <span>yield</span> <span>a</span>
        <span>a</span><span>,</span> <span>b</span> <span>=</span> <span>b</span><span>,</span> <span>a</span><span>+</span><span>b</span>


```

...to statically typed Python

```


<span>def</span> <span>fib</span><span>(</span><span>n</span><span>:</span> <span>int</span><span>)</span> <span>-&gt;</span> <span>Iterator</span><span>[</span><span>int</span><span>]:</span>
    <span>a</span><span>,</span> <span>b</span> <span>=</span> <span>0</span><span>,</span> <span>1</span>
    <span>while</span> <span>a</span> <span>&lt;</span> <span>n</span><span>:</span>
        <span>yield</span> <span>a</span>
        <span>a</span><span>,</span> <span>b</span> <span>=</span> <span>b</span><span>,</span> <span>a</span><span>+</span><span>b</span>


```

Type declarations act as machine-tested documentation, and static typing makes your code clear and easy to modify without making errors.

**[Prospector](https://prospector.landscape.io/en/master)**

Prospector is a powerful static analysis tool for Python code. It displays information about errors, potential problems, convention violations, and complexity. It brings together the functionality of other analysis tools such as:

-   PyLint - Code quality/Error detection/Duplicate code detection
-   pep8.py - [PEP8](https://www.python.org/dev/peps/pep-0008/) code quality
-   pep257.py - [PEP27](https://www.python.org/dev/peps/pep-0257/) Comment quality
-   [pyflakes](https://github.com/PyCQA/pyflakes) - Error detection
-   [mccabe](https://github.com/pycqa/mccabe) - Cyclomatic Complexity Analyser
-   [dodgy](https://github.com/landscapeio/dodgy) - secrets leak detection
-   [pyroma](https://github.com/regebro/pyroma) - setup.py validator
-   [vulture](https://github.com/jendrikseipp/vulture) - unused code detection

Prospector has a number of settings to suppress picky warnings from `pylint`, `pep8` or `pyflakes` and provide only what is important.

**[Bandit](https://github.com/PyCQA/bandit)**

Bandit is a tool developed to find common security issues in Python code. To do this, it analyzes every file, builds an AST from it, and runs suitable plugins to the AST nodes. Once it has completed static analysis for security issues on all of the documents, it generates a report. It can look for Hardcoded passwords, Invalid pickle serialization/deserialization, Shell injections, and SQL injections.

**[Automated Static Code Analysis](https://deepsource.io/)**

You can also automate the static code analysis that can help you develop the culture of creating quality code. Automating the static code analysis saves a lot of time. It helps to identify the issues that may not be detected otherwise.

**Features & Capabilities**

Most of the automated static code analysis tools offer the following features:

-   Multiple programming language support
-   Various security and industry-standard libraries
-   Code standardization
-   Reporting and analytics dashboards
-   Some offer third party integrations, including Github and Jenkins

A perfect example of an automated static analysis and code review tool is [DeepSource](http://deepsource.io/). You can use it for free on Open-Source projects.

[![Alt Text](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fnrf7uqkjaweeds135cx4.png)](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fnrf7uqkjaweeds135cx4.png)
