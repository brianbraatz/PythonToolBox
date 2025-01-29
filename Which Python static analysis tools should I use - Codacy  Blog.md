---
Description: Which Python static analysis tools should I use? - Codacy | Blog
Notes: We take a deep dive into various popular Python static code analysis tools and explain how they can help developers maintain code quality.
author: Codacy
Url: https://blog.codacy.com/python-static-analysis-tools
Created: "2025-01-29  03:10:33"
Modified: 
Tags:
---

# Which Python static analysis tools should I use? - Codacy | Blog

source: https://blog.codacy.com/python-static-analysis-tools

> ## Excerpt
> We take a deep dive into various popular Python static code analysis tools and explain how they can help developers maintain code quality.

---
![python static analysis tools](https://7370416.fs1.hubspotusercontent-na1.net/hub/7370416/hubfs/Neutral%20-%20Dark%20-%20A-1.jpg?width=1740&height=876&name=Neutral%20-%20Dark%20-%20A-1.jpg)

Python, known for its readability and versatility, has become a programming language of choice for many developers. As projects grow in complexity, ensuring code quality and security becomes paramount, and this is where Python static analysis tools emerge as unsung heroes.

[Static code analysis](https://blog.codacy.com/static-code-analysis) involves the examination of an application's source code without its actual execution, revealing potential errors, security vulnerabilities, dependencies, bugs, and other issues embedded within the codebase.

[Static code analysis tools](https://blog.codacy.com/static-code-analysis-tools) are pivotal in scrutinizing code without executing it, identifying potential issues, and enforcing [coding standards](https://blog.codacy.com/coding-standards).

Whether you're a seasoned Python developer looking to enhance your codebase or a newcomer eager to adopt best practices from the outset, static analysis tools can be your best friend. 

Here are a few excellent Python static analysis tools to check out. 

## mypy

[mypy](https://mypy-lang.org/) is a Python static type checker. It aims to enforce more disciplined coding practices by checking and inferring variable types, helping catch potential bugs early in development.

It also integrates with most popular integrated development environments (IDEs) to provide real-time feedback. Mypy also supports gradual typing, allowing developers to adopt it incrementally.

Gradual typing is an approach that allows a programming language to support both static typing and dynamic typing within the same codebase. It provides a smooth transition between the two typing systems, allowing developers to choose when and where to use static typing.

Static typing refers to a feature where variable types are explicitly declared and checked at compile time before the program is run. In statically typed languages, the data types of variables are determined and enforced during the compilation phase rather than at runtime, which is where variable types are checked and resolved when using dynamically typed languages.

Python is traditionally a dynamically typed language, meaning you don't need to declare a variable's data type explicitly. The variable type is determined at runtime based on the value it holds. 

In recent versions of Python, however, there has been a move towards incorporating static typing through tools like "Type Hints." Type Hints allow developers to add type information to their code using annotations voluntarily. Static analysis tools like MyPy can use these hints to catch potential type-related errors before the code is run.

```
<span><span>#</span><span> </span><span>Type</span><span> </span><span>Hints</span><span> </span><span>in</span><span> </span><span>Python</span><span> </span><span>3.5</span><span>+</span></span><br><span><span>def</span><span> </span><span>add_numbers</span><span>(</span><span>a</span><span>: </span><span>int</span><span>, </span><span>b</span><span>: </span><span>int</span><span>) -&gt; </span><span>int</span><span>:</span></span><br><span><span>&nbsp;&nbsp;&nbsp;</span><span>return</span><span> </span><span>a</span><span> +&nbsp;</span><span>b</span></span><br><br><span><span>result</span><span> = </span><span>add_numbers</span><span>(</span><span>5</span><span>, </span><span>10</span><span>)</span></span><br><span><span>print</span><span>(</span><span>result</span><span>)&nbsp; </span><span>#</span><span> </span><span>Output</span><span>: </span><span>15</span></span>
```

MyPy enables you to write statically typed code while verifying the correctness of your types. 

## Pylint

[Pylint](https://www.pylint.org/) is a widely used static code analysis tool that checks for coding standards and other coding errors, offering suggestions for improvement. It provides a comprehensive analysis covering various coding rules and potential issues.

Pylint is also easily configurable and extensible, allowing developers to tailor checks to their preferences. It can also be very helpful when refactoring code, enabling you to detect unused and duplicated code easily. 

```
<span><span>************* </span><span>Module</span><span> </span><span>example<br><span>W</span><span>:&nbsp; </span><span>2</span><span>, </span><span>0</span><span>: </span><span>Unused</span><span> </span>add_numbers<span> </span>imported<span> </span><span>from</span><span> </span>example<span> (</span>unused<span>-</span><span>import</span><span>)</span><br><span>C</span><span>:&nbsp; </span><span>6</span><span>, </span><span>0</span><span>: </span><span>Duplicate</span><span> </span>code<span> </span><span>for</span><span> </span><span>'add_numbers'</span><span> </span>at<span> </span>line<span> </span><span>6</span><span> (</span>duplicate<span>-</span>code<span>)</span><br><span>R</span><span>: </span><span>12</span><span>, </span><span>4</span><span>: </span><span>Too</span><span> </span>many<span> </span>statements<span> (</span><span>14</span><span>/</span><span>10</span><span>) (</span>too<span>-</span>many<span>-</span>statements<span>)</span></span></span>
```

You’re also able to write your own plugins for Pylint to add more personalized features. 

## Pyflakes

[Pyflakes](https://pypi.org/project/pyflakes/) is a lightweight static analysis tool focused on identifying errors in Python code.

It’s fast and efficient, providing quick feedback during development. It’s also simple to use and suitable for integration into various workflows.

Pyflakes doesn’t focus on style. Instead, it focuses on logical code issues, errors in a program that do not cause syntax errors but result in incorrect or unintended behavior due to flawed logic or reasoning in the code.

If you also want style checks, you should check out [flake8](https://pypi.org/project/flake8/), which combines Pyflakes with style checking against the [PEP 8](https://peps.python.org/pep-0008/) Python style guide. 

The creators of Pyflakes claim that it rarely emits false positives and that it’s faster than Pylint.

## pycodestyle

Formerly known as pep8, [pycodestyle](https://pypi.org/project/pycodestyle/) focuses on enforcing the style guide outlined in PEP 8. It’s straightforward and effective for maintaining code style consistency and easy to integrate. 

If you want to check your code against the style conventions of PEP 8, this is the official [linter](https://blog.codacy.com/what-is-a-linter) for that purpose. You can get pycodestyle to show the source code for each error with the relevant text from PEP 8, which would look something like this: 

```
<span><span>example</span><span>.</span><span>py</span><span>:</span><span>3</span><span>:</span><span>12</span><span>: </span><span>E703</span><span> </span><span>statement</span><span> </span><span>ends</span><span> </span><span>with</span><span> </span><span>a</span><span> </span><span>semicolon<br>example<span>.</span>py<span>:</span><span>3</span><span>:</span><span>12</span><span>: </span><span>E225</span><span> </span>missing<span> </span>whitespace<span> </span>around<span> </span>operator<br></span><span>example</span><span>.</span><span>py</span><span>:</span><span>3</span><span>:</span><span>17</span><span>: </span><span>E703</span><span> </span><span>statement</span><span> </span><span>ends</span><span> </span><span>with</span><span> </span><span>a</span><span> </span><span>semicolon</span></span>
```

The above output indicates that there are issues with the code:

-   **E703:** PEP 8 does not recommend using semicolons to terminate statements in Python. A newline typically terminates statements. The error suggests that the statement ends with a semicolon.
-   **E225:** PEP 8 recommends adding whitespace around binary operators to improve readability. The error suggests that there is missing whitespace around the + operator.

## Bandit

[Bandit](https://bandit.readthedocs.io/en/latest/) is a security-focused static analysis tool that detects security vulnerabilities like [hard-coded passwords](https://blog.codacy.com/hard-coded-secrets), shell injections, [SQL injections](https://blog.codacy.com/injection-attacks-owasp-top-10), and invalid pickle serialization/deserialization.

It integrates well into continuous integration/continuous delivery (CI/CD) pipelines to perform ongoing security checks as you code.

The only real shortcoming of Bandit is that it’s limited to security-related issues and may not catch broader coding issues. Like most other code security tools, Bandit may sometimes produce false positives.

## PMD CPD

[PMD’s Copy/Paste Detector (CPD)](https://pmd.github.io/pmd/pmd_userdocs_cpd) helps developers locate duplicate code. It works with Python and many other popular programming languages, including Java, C/C++, C#, Go, Ruby, Swift, and more.

Why is it essential to be able to locate duplicate blocks of code? If identical code blocks serve the same purpose, any effort to restructure them, even in a simple manner, leads to repetitive manual grunt work. Locating every instance of duplicate code that requires refactoring is another tedious task when performed manually. 

A tool like PMD CPD can help you find the duplicates and take them out of your code so that you can avoid refactoring altogether.

## Radon and McCabe

Both [Radon](https://pypi.org/project/radon/) and [McCabe](https://pypi.org/project/mccabe/) help developers analyze and measure code complexity. Radon calculates cyclomatic complexity and the maintainability index of your code.

Cyclomatic Complexity measures program complexity by counting the number of independent paths through its source code. A higher cyclomatic complexity indicates greater code complexity and may suggest a need for simplification or refactoring.

The maintainability index quantifies how maintainable and understandable a program's source code is, considering factors such as cyclomatic complexity, code size, and duplication. The higher your maintainability index score, the more maintainable your code appears to be.

McCabe also measures the cyclomatic complexity of your functions. It's a good option if you want a no-frills tool focused on that one metric and nothing else. 

## Prospector

[Prospector](https://pypi.org/project/prospector/) is a tool that combines various Python analysis tools to provide a holistic view of [code quality](https://blog.codacy.com/code-quality-explained). It’s highly customizable and allows you to tailor which tools are included in your analysis. 

It’s also easily integrated into tools like Jenkins, CircleCI, GitHub, and GitLab.

Prospector runs several of the tools we’ve already discussed and some additional ones. The default options include: 

-   **Pylint**  
    
-   **pycodestyle**  
    
-   **Pyflakes**  
    
-   **Pyflakes**   
    
-   **Pydocstyle**  
    
-   **McCabe**

It also includes **Dodgy**, a [secret detection tool](https://blog.codacy.com/new-security-and-risk-management-features#SecretDetection). 

Some option extras you can add to Prospector include: 

-   **Mypy**
-   **Bandit**
-   **Pyroma**, a tool that ensures best practices of the Python packaging ecosystem and warns you if you’re missing any package metadata that could improve package quality. 
-   **Vulture**, which finds unused classes, functions, and variables
-   **Frosted**, a fork of pyflakes created to extend pyflakes development at a time when development slowed for the tool. 

Prospect is a bit resource-intensive since so many tools are packaged together, especially when reviewing larger codebases. 

A code quality platform like Codacy gives you access to many popular Python static analysis tools under one roof. With Codacy, every time you run static analysis on your code, it’s being reviewed by Bandit, Prospector, Pylint, PMD CPD, and Radon. 

Codacy even integrates with popular security scanner [Trivy](https://trivy.dev/), which runs secrets and [insecure dependencies detection](https://blog.codacy.com/insecure-dependencies-detection). Check out our list of supported languages and tools to get a full rundown of Codacy’s integrations and features. 

[Sign up for a free trial today](https://www.codacy.com/signup-codacy) to see how easy it is to perform static code analysis with Codacy,  no matter your preferred programming language.
