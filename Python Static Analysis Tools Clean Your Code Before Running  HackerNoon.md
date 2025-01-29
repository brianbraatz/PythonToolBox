---
Description: "Python Static Analysis Tools: Clean Your Code Before Running | HackerNoon"
Notes: Review of essential modern Python code static analysis tools.
author: Taras Drapalyuk
Url: https://hackernoon.com/python-static-analysis-tools-clean-your-code-before-running
Created: 2025-01-29  03:11:14
Modified: 
tags:
---

# Python Static Analysis Tools: Clean Your Code Before Running | HackerNoon

source: https://hackernoon.com/python-static-analysis-tools-clean-your-code-before-running

> ## Excerpt
> Review of essential modern Python code static analysis tools.

---
One of the major software engineering principles is that the earlier a defect is found, the more cheaply it can be solved. In this article, I'll go through the most popular tools nowadays that check your code even before running it. These tools work with the principle of static analysis, meaning they treat code as text (in simpler terms). I picked only the most popular and sufficiently maintained ones.

![https://www.reddit.com/r/ProgrammerHumor/comments/12mqjhz/the_difference/](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

https://www.reddit.com/r/ProgrammerHumor/comments/12mqjhz/the\_difference/

## Linters

Alright, so first things first, let's talk about what a linter is. So there's this tool called "lint" that was originally designed to analyze C source code. It's like a lint trap in a clothes dryer, except it catches small program bugs instead. This utility was created by Stephen C. Johnson back in 1978 when he was working at Bell Labs. The original lint tool and other similar utilities were mainly used to analyze source code to optimize compilers. But over time, these lint-like tools started doing a whole lot more, like performing other types of checks and verifications.

### Code style/errors checkers

**1\. Pyflakes**

[https://github.com/PyCQA/pyflakes](https://github.com/PyCQA/pyflakes?ref=hackernoon.com)

A simple tool which checks Python source files for errors. Pyflakes makes a simple promise: it will never complain about style, and it will try very, very hard to never emit false positives.

**2\. Pycodestyle (formerly called pep8)**

[https://github.com/PyCQA/pycodestyle](https://github.com/PyCQA/pycodestyle?ref=hackernoon.com)

Pycodestyle is a tool to check your Python code against some of the style conventions in [PEP 8](http://www.python.org/dev/peps/pep-0008/?ref=hackernoon.com).

**3\. Pydocstyle**

[https://github.com/PyCQA/pydocstyle](https://github.com/PyCQA/pydocstyle?ref=hackernoon.com)

Same as Pycodestyle but it checks docstring conventions.

**4\. Pylint**

[https://github.com/pylint-dev/pylint](https://github.com/pylint-dev/pylint?ref=hackernoon.com)

Pylint analyses your code without actually running it. It checks for errors, enforces a coding standard, looks for [code smells](https://martinfowler.com/bliki/CodeSmell.html?ref=hackernoon.com), and can make suggestions about how the code could be refactored.

**5\. Pyroma**

[https://github.com/regebro/pyroma](https://github.com/regebro/pyroma?ref=hackernoon.com)

It's a package style checker that rates how well your project complies with the best practices of the Python packaging ecosystem and lists issues that could be improved. Useful for authors of public libraries.

**6\. Vulture**

[https://github.com/jendrikseipp/vulture](https://github.com/jendrikseipp/vulture?ref=hackernoon.com)

It finds dead Python code, including unused classes, functions, and variables. It's a great tool for refactoring your code.

![image](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

**7\. Bandit**

[https://github.com/PyCQA/bandit](https://github.com/PyCQA/bandit?ref=hackernoon.com)

Bandit is a tool designed to find common security issues in Python code.

### Type checkers

Type checkers help ensure that variables and functions in your code are consistent with each other in terms of type.

![image](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

**1\. Mypy**

[https://github.com/python/mypy](https://github.com/python/mypy?ref=hackernoon.com)

Mypy is a pioneer in the world of Python type checkers. It was written by Jukka Lehtosalo in 2012 with further contributions from Guido van Rossum, Ivan Levkivskyi, and many others over the years. With mypy, add type hints (**[PEP 484](https://peps.python.org/pep-0484/?ref=hackernoon.com)**) to your Python programs, and mypy will warn you when you use those types incorrectly. For a detailed history, refer to [this documentation](http://mypy-lang.org/about.html?ref=hackernoon.com).

**2\. Pyright (Microsoft)**

[https://github.com/Microsoft/pyright](https://github.com/Microsoft/pyright?ref=hackernoon.com)

The first public release was in 2019. Pyright is a full-featured, standards-based static type checker for Python. It is designed for **high performance** and can be used with **large** Python **source bases**. Pyright uses its own parser, which can recover from syntax errors and continue parsing. In contrast, mypy uses the parser built into the Python interpreter and cannot recover from syntax errors. Additionally, mypy uses a traditional multi-pass architecture where semantic analysis is performed multiple times on a module until all types converge. Therefore, pyright is **3-5 times faster than mypy**. For more details, see [here](https://microsoft.github.io/pyright/?ref=hackernoon.com#/mypy-comparison).

**3\. Pyre (Facebook)**

[https://github.com/facebook/pyre-check](https://github.com/facebook/pyre-check?ref=hackernoon.com)

Type checker which is written in OCaml. Open-sourced in 2018, Pyre is a performant type checker for Python that is compliant with [PEP 484](https://www.python.org/dev/peps/pep-0484/?ref=hackernoon.com). It is **faster than mypy** due to running multiple checkers in parallel, and uses bottom-up static analysis. It has a built-in security checker called **Pysa**, which is actually on top of Pyre. It comes with tooling that helps you gradually update your codebase with type hinting.

**4\. Pytype (Google)**

[https://github.com/google/pytype](https://github.com/google/pytype?ref=hackernoon.com)

Pytype checks and infers types for your Python code - **without requiring type annotations**. Google developed this tool for its gigantic monolithic repository; thus, this tool is especially useful for checking large codebases.

### Code complexity checkers

These tools will help you maintain your code more readable. The most popular way is to calculate cyclomatic complexity, which is a number used to show how complex a program is. It measures the number of paths that can be taken through a program's code. It was created by Thomas J. McCabe, Sr. in 1976.

**1\. McCabe**

[https://github.com/PyCQA/mccabe](https://github.com/PyCQA/mccabe?ref=hackernoon.com)

Simple McCabe complexity checker. It can be used as a standalone solution, as well as a plugin for **flake8**.

**2\. Radon**

[https://github.com/rubik/radon](https://github.com/rubik/radon?ref=hackernoon.com)

Radon is a Python tool that computes various metrics from the source code:

-   **McCabe's complexity**, i.e. cyclomatic complexity
-   **Raw** metrics (including Source Lines of Code, comment lines, blank lines, etc.).
-   **Halstead** metrics ([wiki](https://en.wikipedia.org/wiki/Halstead_complexity_measures?ref=hackernoon.com))
-   **Maintainability Index** (the one used in Visual Studio)

**3\. Wily**

[https://github.com/tonybaloney/wily](https://github.com/tonybaloney/wily?ref=hackernoon.com)

A command-line application for tracking and reporting on the complexity of Python tests and applications. It can analyze commits and build a report to show how complexity changes and whose commit ruins this metric :)

## Formatters

Code formatter is a tool that automatically format code according to certain standards or rules. They can format code to be more readable, consistent, and maintainable. Some formatters use their own rules, while others use the linter's output. Here are some examples of what formatters can do: sorting imports, formatting docstrings, formatting code to conform to style guides such as [PEP 8](https://peps.python.org/pep-0008/?ref=hackernoon.com) and [PEP 257](https://www.python.org/dev/peps/pep-0257/?ref=hackernoon.com), and so on.

Code formatting tools seriously save so much time when you're trying to stick to a style guide. You just set it up once and let it do its thing automatically. Plus, it makes your pull request **diffs** so much **easier to read**.

![https://www.reddit.com/r/ProgrammerHumor/comments/pszopm/little_contribution_to_the_indentation_war/](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

https://www.reddit.com/r/ProgrammerHumor/comments/pszopm/little\_contribution\_to\_the\_indentation\_war/

**1\. Isort**

[https://github.com/PyCQA/isort](https://github.com/PyCQA/isort?ref=hackernoon.com)

This is a very useful tool for keeping imports in your code organized.

**2\. Docformatter**

[https://github.com/PyCQA/docformatter](https://github.com/PyCQA/docformatter?ref=hackernoon.com)

Automatically formats docstrings to follow a subset of the PEP 257 conventions.

**3\. Pydocstringformatter**

[https://github.com/DanielNoord/pydocstringformatter](https://github.com/DanielNoord/pydocstringformatter?ref=hackernoon.com)

This project is heavily inspired by **docformatter**. This tool automatically formats Python docstrings to follow recommendations from [PEP 8](https://www.python.org/dev/peps/pep-0008/?ref=hackernoon.com) and [PEP 257](https://www.python.org/dev/peps/pep-0257/?ref=hackernoon.com) (or other supported style guides).

**4\. Black**

[https://github.com/psf/black](https://github.com/psf/black?ref=hackernoon.com)

I'd better provide a quote from the project description:

> _Black_ is the uncompromising Python code formatter. By using it, you agree to cede control over minutiae of hand-formatting. In return, _Black_ gives you speed, determinism, and freedom from **pycodestyle** nagging about formatting. You will save time and mental energy for more important matters.

> Blackened code looks the same regardless of the project you're reading. Formatting becomes transparent after a while and you can focus on the content instead.

**5\. YAPF (Yet Another Python Formatter by Google)**

[https://github.com/google/yapf](https://github.com/google/yapf?ref=hackernoon.com)

More flexible compared to Black. You can configure your own style guide or rely on one of the predefined ones:

-   **pep8** (default)
-   **google** (based on the [Google Python Style Guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md?ref=hackernoon.com))
-   **yapf** (for use with Google open-source projects)
-   **facebook**

**6\. Autoflake**

[https://github.com/PyCQA/autoflake](https://github.com/PyCQA/autoflake?ref=hackernoon.com)

Removes unused imports and unused variables as reported by **pyflakes**.

**7\. Pyupgrade**

[https://github.com/asottile/pyupgrade](https://github.com/asottile/pyupgrade?ref=hackernoon.com)

A tool to automatically upgrade syntax for newer versions of the language. Very handy in keeping the code style consistent with the most recent version of Python.

**8\. Autopep8**

[https://github.com/hhatto/autopep8](https://github.com/hhatto/autopep8?ref=hackernoon.com)

Automatically formats Python code to conform to the [PEP 8](https://www.python.org/dev/peps/pep-0008/?ref=hackernoon.com) style guide. It uses the **pycodestyle** utility to determine which parts of the code need to be formatted.

## Multi-tools

In this category, I include utilities that can perform multiple tasks right out of the box or be customized to fit your needs using plugins.

![image](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

**1\. Flake8**

[https://github.com/PyCQA/flake8](https://github.com/PyCQA/flake8?ref=hackernoon.com)

Flake8 is a Python tool that glues together **pycodestyle**, **pyflakes**, **mccabe**, and third-party plugins to check the style and quality of some Python code.

**2\. Ruff**

[https://github.com/charliermarsh/ruff](https://github.com/charliermarsh/ruff?ref=hackernoon.com)

Ruff can be used to replace Flake8 (plus dozens of plugins), isort, pydocstyle, yesqa, eradicate, pyupgrade, and autoflake, all while executing **tens or hundreds of times faster** than any individual tool. It’s incredibly fast!

**3\. Prospector**

[https://github.com/PyCQA/prospector](https://github.com/PyCQA/prospector?ref=hackernoon.com)

Inspects Python source files and provides information about type and location of classes, methods etc. It brings together the functionality of other Python analysis tools such as Pylint, pycodestyle, and McCabe complexity. See the [Supported Tools](https://prospector.readthedocs.io/en/latest/supported_tools.html?ref=hackernoon.com) documentation section for a complete list.

## How to run

You can run checkers **directly** on your computer from time to time, but it's not the best option, as there is a risk of forgetting to do so. It's better to implement auto checkers (see below) first and have the option to run them directly as a more convenient way to debug.

Using **pre-commit** on your computer, you can prevent committing unchecked code, which is convenient. However, don't forget to set up the pre-commit hook right after cloning a repository.

Using a **dedicated CI step** (in GitHub Actions or GitLab CI/CD) is the most reliable way to check code, no matter where it came from.

## Conclusion

Static analysis tools for Python code are essential for catching defects early in the development process. Integrating these tools into your workflow can save time and improve code quality, leading to a better end product. I think at least a general code formatter (**Black** or **YAPF**) and a type checker (I prefer **mypy**) should be used for any projects. The earlier you configure them, the less time you will spend fixing problems in the future.

## References

-   [Lint (software) - Wikipedia](https://en.wikipedia.org/wiki/Lint_(software)?ref=hackernoon.com)
-   [Martin Fowler - CodeSmell](https://martinfowler.com/bliki/CodeSmell.html?ref=hackernoon.com)
-   [Cyclomatic complexity - Wikipedia](https://en.wikipedia.org/wiki/Cyclomatic_complexity?ref=hackernoon.com)
-   [Halstead complexity measures - Wikipedia](https://en.wikipedia.org/wiki/Halstead_complexity_measures?ref=hackernoon.com)

## Videos

Here is some additional video material about the tools that I mentioned in this article.

### Black

<iframe src="https://www.youtube.com/embed/esZLCuWs_2Y" title="ytcontainer" width="700" height="394" frameborder="0" data-iub-purposes="3,s" data-cmp-ab="2" data-cmp-src="https://www.youtube.com/embed/esZLCuWs_2Y" data-cmp-info="11" data-cmp-vendor="179" async="false"></iframe>

### Pyre

<iframe src="https://www.youtube.com/embed/hWV8t494N88" title="ytcontainer" width="700" height="394" frameborder="0" data-iub-purposes="3,s" data-cmp-ab="2" data-cmp-src="https://www.youtube.com/embed/hWV8t494N88" data-cmp-info="11" data-cmp-vendor="179" async="false"></iframe>

### Pytype

<iframe src="https://www.youtube.com/embed/abvW0mOrDiY" title="ytcontainer" width="700" height="394" frameborder="0" data-iub-purposes="3,s" data-cmp-ab="2" data-cmp-src="https://www.youtube.com/embed/abvW0mOrDiY" data-cmp-info="11" data-cmp-vendor="179" async="false"></iframe>
