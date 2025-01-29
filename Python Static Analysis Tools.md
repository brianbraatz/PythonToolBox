---
Description: Python Static Analysis Tools
Notes: "Those tools are specifically designed to hurt an engineer's feelings: they tell you when the code smells, even when the code itself executes fine."
author: luminousmen
Url: https://luminousmen.com/post/python-static-analysis-tools/
Created: 2025-01-29  03:10:49
Modified: 
tags:
---

# Python Static Analysis Tools

source: https://luminousmen.com/post/python-static-analysis-tools/

> ## Excerpt
> Those tools are specifically designed to hurt an engineer's feelings: they tell you when the code smells, even when the code itself executes fine.

---
Development teams are under pressure. Releases must be delivered on time. Coding and quality standards must be met. And errors are not an option. That's why development teams use static analysis.

[

## Why use static analysis?

](https://luminousmen.com/post/python-static-analysis-tools/#why-use-static-analysis)

The main work of static code analysis tools is to analyze source code or compiled code so that you could easily detect vulnerabilities without executing a program.

👍 Provides consistency in engineering teams

👍 Provides insight into code without executing it

👍 Executes quickly in comparison with dynamic analysis

👍 Can automate code quality maintenance

👍 Can automate the search for bugs at the early stages (although not all)

👍 Can automate the finding of security problems at an early stage

👍 You are already using it (if you use any IDE that already has static analyzers, Pycharm uses pep8 for example).

[

## What types of static analysis exist?

](https://luminousmen.com/post/python-static-analysis-tools/#what-types-of-static-analysis-exist)

-   Code styling analysis
-   Security linting
-   Error detection
-   UML diagram creation
-   Duplicate code detection
-   Complexity analysis
-   Comment styling analysis
-   Unused code detection

Let's move on to the tools that exist in the Python ecosystem for static analysis:

[

## 1\. Mypy

](https://luminousmen.com/post/python-static-analysis-tools/#-mypy)

**[Mypy Official Website](http://mypy-lang.org/)**

If you have only ever used dynamically typed Python, you might wonder about all the fuss about static typing. You may even enjoy Python because it has dynamic typing, and the whole thing may be a bit baffling.

The key to static type checking is scale — the larger your project, the more you want it. Type declarations act as machine-tested documentation, and static typing makes your code clearer and easier to modify without making errors. This is a problem where mypy can help.

Mypy is the de facto static type checker for Python. It acts as a linter that allows you to write statically typed code and verify that types in your project are correct.

The requirement here is that your code is annotated, using Python 3 function annotation syntax ([PEP484](https://www.python.org/dev/peps/pep-0484/)). Then, mypy can type check your code and find common bugs. Its purpose is to combine the advantages of dynamic and static typing (using a typing module).

Installation is simple:

```bash
$ python -m pip install mypy
```

Usage:

```bash
$ mypy *.py
```

You should see a similar output if no errors are found.

```bash
Success: no issues found in N source files
```

You can configure Mypy using a configuration file `mypy.ini`. Just FYI, your target configuration should include, at minimum, the following configurations:

```markup
disallow_untyped_defs = true no_implicit_optional = true show_error_codes = true strict_equality = true warn_redundant_casts = true warn_unused_ignores = true
```

Of course, there are other possibilities for mypy, but we'll move on to the next tool.

[

## 2\. Pylint

](https://luminousmen.com/post/python-static-analysis-tools/#-pylint)

**[Pylint Official Website](https://pylint.org/)**

Well known in the community, Python **pylint** is number two on my list. It has a number of features, from coding standards compliance to bug detection, and helps with refactoring (by detecting duplicate or unused code).

Pylint is overly pedantic out of the box and benefits from a minimal configuration effort, but it is fully customizable through a `.pylintrc` file where you can choose which errors or agreements are relevant to you.

You can easily install pylint:

```bash
$ python -m pip install pylint
```

Running Pylint on a piece of code will result in something like this (which will be followed by some statistics):

```markup
$ pylint app.py C:122, 4: Missing method docstring (missing-docstring) R:136, 0: Too many instance attributes (9/7) (too-many-instance-attributes) R:217, 4: Too many local variables (23/15) (too-many-locals) C:345,16: Variable name "mo" doesn't conform to snake_case naming style (invalid-name) R:304, 8: Too many nested blocks (6/5) (too-many-nested-blocks) C:377,24: Variable name "mo" doesn't conform to snake_case naming style (invalid-name) W:403,34: Access to a protected member _payload of a client class (protected-access) R:304, 8: Too many nested blocks (6/5) (too-many-nested-blocks) C:405,28: Variable name "mo" doesn't conform to snake_case naming style (invalid-name) W:408,32: Access to a protected member _payload of a client class (protected-access) R:304, 8: Too many nested blocks (6/5) (too-many-nested-blocks) W:268,16: Unused variable 'msg' (unused-variable) R:217, 4: Too many return statements (7/6) (too-many-return-statements) R:217, 4: Too many branches (58/12) (too-many-branches) R:217, 4: Too many statements (160/50) (too-many-statements)
```

Note that Pylint prefixes each of the problem areas with an `R`, `C`, `W`, `E`, or `F`, meaning:

\[R\]efactor for "good practice" metric violation \[C\]onvention for coding standard violation \[W\]arning for stylistic problems, or minor programming issues \[E\]rror for important programming issues (i.e. most probably a bug) \[F\]atal for errors which prevented further processing

Regarding the coding style, Pylint follows the [PEP8](https://www.python.org/dev/peps/pep-0008/) style guide.

Pylint comes with [Pyreverse](https://www.logilab.org/blogentry/6883), which helps you create UML diagrams for your code.

You can also write plugins to add your own features.

[

## 3\. Pyflakes

](https://luminousmen.com/post/python-static-analysis-tools/#-pyflakes)

**[Pyflakes Official Website](https://pypi.org/project/pyflakes/)**

Pyflakes' approach is similar to the previous one, but it tries very hard not to produce false positives. Pyflakes "makes a simple promise: it will never complain about style, and it will try very, very hard to never emit false positives". This means that Pyflakes will not tell you about the missing docstrings or argument names that do not match the naming style. It focuses on logical code issues and potential errors.

Pyflakes only examines the syntax tree of each file individually. This, combined with a limited set of errors, makes it faster than pylint. On the other hand, pyflakes are more limited in what it can check.

It can be installed with:

```bash
$ python -m pip install pyflakes
```

Usage:

```bash
$ pyflakes script.py crummy_code.py:1: 'sys' imported but unused crummy_code.py:15: undefined name 'platform'
```

Although pyflakes do not do any stylistic checks, there is another tool that combines pyflakes with PEP8 style checks: [flake8](http://flake8.pycqa.org/en/latest/).

[

## 4\. pycodestyle aka pep8

](https://luminousmen.com/post/python-static-analysis-tools/#-pycodestyle-aka-pep)

**[pycodestyle Official Website](https://pypi.org/project/pycodestyle/)**

This package used to be called `pep8` but was renamed to `pycodestyle` to reduce confusion. `pycodestyle` is the official linter to check the python code against the style conventions of [PEP8](https://peps.python.org/pep-0008/).

To install it:

```bash
$ python -m pip install pycodestyle
```

Simple CLI usage:

```bash
$ pycodestyle --first optparse.py optparse.py:69:11: E401 multiple imports on one line optparse.py:77:1: E302 expected 2 blank lines, found 1 optparse.py:88:5: E301 expected 1 blank line, found 0 optparse.py:222:34: W602 deprecated form of raising exception optparse.py:347:31: E211 whitespace before '(' optparse.py:357:17: E201 whitespace after '{' optparse.py:472:29: E221 multiple spaces before operator optparse.py:544:21: W601 .has_key() is deprecated, use 'in'
```

Just to be clear — pycodestyle does not enforce every single rule of PEP 8. It just helps to verify that some coding conventions are applied but it does not intend to be exhaustive. Some rules cannot be expressed with a simple algorithm, and other rules are only guidelines which you could circumvent when you need to.

[

## 5\. Flake8

](https://luminousmen.com/post/python-static-analysis-tools/#-flake)

**[Flake8 Official Website](http://flake8.pycqa.org/en/latest/)**

Flake8 is a wrapper around [pyflakes](https://pypi.org/project/pyflakes/), [pycodestyle aka pep8](https://pypi.org/project/pycodestyle/) and [circular complexity checker](https://github.com/pycqa/mccabe) (which is used to detect complex-code).

Installing Flake8 is pretty easy:

```bash
$ python -m pip install flake8
```

Usage:

```bash
$ flake8 app.py --statistics app.py:2:1: F401 'os' imported but unused app.py:2:1: F401 'sys' imported but unused app.py:2:10: E401 multiple imports on one line app.py:3:1: F401 'logging' imported but unused app.py:4:1: F401 '..views' imported but unused app.py:6:1: E302 expected 2 blank lines, found 1 app.py:6:19: F821 undefined name 'SomeCommand' app.py:6:31: E203 whitespace before ':' app.py:9:25: E231 missing whitespace after ','app.py:13:37: W291 trailing whitespace app.py:16:21: E701 multiple statements on one line (colon) app.py:16:34: W291 trailing whitespace app.py:17:13: E271 multiple spaces after keyword app.py:17:14: E203 whitespace before ':'
```

The error code of flake8 are:

-   E\*\*\*/W\*\*\*: Errors and warnings of pycodestyle
-   F\*\*\*: Detections of PyFlakes
-   C9\*\*: Detections of circulate complexity by McCabe-script

This is my personal favorite. Flake8 is inherently modular, brick-like. There are a ton of different plugins for every taste. Flake8 also has a powerful configuration mechanism using `.flake8`, `setup.cfg` or `tox.ini` files. Plugins and warnings can be disabled in every file (or even on every line using the # noqa comment).

[

## 6\. Prospector

](https://luminousmen.com/post/python-static-analysis-tools/#-prospector)

**[Prospector Official Website](https://prospector.landscape.io/en/master)**

One of the powerful static analysis tools for analyzing Python code and displaying information about errors, potential issues, convention violations and complexity. It includes:

✔ PyLint — Code quality/Error detection/Duplicate code detection

✔ pep8.py — [PEP8](https://www.python.org/dev/peps/pep-0008/) code quality

✔ pep257.py — [PEP27](https://www.python.org/dev/peps/pep-0257/) Comment quality

✔ [pyflakes](https://github.com/PyCQA/pyflakes) — Error detection

✔ [mccabe](https://github.com/pycqa/mccabe) — Cyclomatic Complexity Analyser

✔ [dodgy](https://github.com/landscapeio/dodgy) — secrets leak detection

✔ [pyroma](https://github.com/regebro/pyroma) — setup.py validator

✔ [vulture](https://github.com/jendrikseipp/vulture) — unused code detection

Most of the warnings coming from tools such as pylint, pep8 or pyflakes are likely to be a bit picky. There are warnings about line lengths, warnings about spaces on empty lines, warnings about how much space there is between methods in your class, etc. What you really need, however, is a list of the real problems in your code. Because of this, Prospector has a number of settings and default behavior to suppress the more nagging warnings and provide only what's important.

It's my another favorite tool for static analysis because of its power, customizations for the team, and easy usage.

Installation:

```bash
$ python -m pip install prospector
```

You can customize severity, ignore some errors, and enable/disable tools by providing the `.prospector.yml` file. For example:

```yml
strictness: medium test-warnings: true doc-warnings: true autodetect: false max-line-length: 120 pep8: full: true disable: - N803 # argument name should be lowercase - N806 # variable in function should be lowercase - N812 # lowercase imported as non lowercase pylint: run: true disable: - too-many-locals - arguments-differ - no-else-return - inconsistent-return-statements pep257: run: true disable: - D203 # 1 blank line required before class docstring - D212 # Multi-line docstring summary should start at the first line - D213 # Multi-line docstring summary should start at the second line
```

[

## 7\. Bandit

](https://luminousmen.com/post/python-static-analysis-tools/#-bandit)

**[Bandit Official Website](https://github.com/PyCQA/bandit)**

`bandit` is a tool designed to find common security issues in Python code. It can do:

✔ Static analysis tool to detect security defects

✔ Hardcoded passwords

✔ Invalid pickle serialization/deserialization

✔ Shell injections

✔ SQL injections

Check out how it marks Python's `eval` as an insecure function:

```bash
Test results: >> Issue: [B307:blacklist] Use of possibly insecure function - consider using safer ast.literal_eval. Severity: Medium Confidence: High Location: test.py:3 More Info: https://bandit.readthedocs.io/en/latest/blacklists/blacklist_calls.html#b307-eval print(eval("1+1")) -------------------------------------------------- Code scanned: Total lines of code: 2 Total lines skipped (#nosec): 0 Run metrics: Total issues (by severity): Undefined: 0.0 Low: 0.0 Medium: 1.0 High: 0.0 Total issues (by confidence): Undefined: 0.0 Low: 0.0 Medium: 0.0 High: 1.0 Files skipped (0):
```

Let's look specifically at the section `Test Results'. Here we see that there is a problem marked` B307`and named blacklist. The message usually tells us what the specific problem is and a potential way to fix it. In this case, blacklist means that the`eval\` operator is (and should be) blacklisted.

After that message, we are given information about:

1.  How severe the issue is — Medium in this case
2.  How confident Bandit is that there's a problem — High
3.  Where the issue is — in `test.py` on line number 2
4.  And the code in question, complete with line numbers.

It's pretty straightforward and easy to use.

[

## Conclusion

](https://luminousmen.com/post/python-static-analysis-tools/#conclusion)

To conclude, I would like to say that time invested once in static analysis setup will really benefit you and your team in terms of time spent on searching for errors, explaining code to newcomers in the project, project costs, etc. It may seem to you that you are not working on the product but wasting your time, but don't worry — it will return to you in future.

Those tools are specifically designed to hurt an engineer's feelings: they tell you when the code smells, even when the code itself executes fine. These tools can participate in CI pipelines and in local development.

#### Recommended books

-   [Learning Python by Mark Lutz](https://amzn.to/2KsPnHp)
-   [Learn Python 3 the Hard Way by Zed Shaw](https://amzn.to/3sMGJVw)
-   [Fluent Python: Clear, Concise, and Effective Programming](https://amzn.to/2LJtMLm)

_Thank you for reading! Curious about something or have thoughts to share? Leave your comment below or follow me via [LinkedIn](https://www.linkedin.com/in/luminousmen/), [Substack](https://luminousmen.substack.com/welcome), or [Telegram](https://t.me/iamluminousmen)._
