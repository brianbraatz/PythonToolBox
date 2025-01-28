---
Description: Python scripts - PHYS281
Notes: A Python script is a file that generally contains a short self-contained set of instructions,
i.e., lines of code, that perform a specific task. They are called scripts because they are read and
interpreted by Python line-by-line in order from the first line to the last.
author: Matthew Pitkin, Elisabetta Boella and Neil Drummond
Url: https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts/
Created: "2025-01-28  09:43:23"
Modified: 
Tags:
---

# Python scripts - PHYS281

source: https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts/

> ## Excerpt
> A Python script is a file that generally contains a short self-contained set of instructions,
i.e., lines of code, that perform a specific task. They are called scripts because they are read and
interpreted by Python line-by-line in order from the first line to the last.

---
# Python scripts[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#python-scripts "Permanent link")

<iframe width="560" height="315" src="https://www.youtube.com/embed/FWgddKdrBI0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>

A Python [script](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#script) is a file that generally contains a short self-contained set of instructions, i.e., lines of code, that perform a specific task. They are called scripts because they are read and interpreted by Python line-by-line in order from the first line to the last.

Tip

In reality scripts can be any length and do multiple things, but this is not recommended. If a script file is getting too long it can often be broken into several shorter files, with the required bits imported into a main script (see the tutorial on [importing modules](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-importing-modules/)).

A Python script file usually has the `.py` suffix @(file extension). File names can be anything that your operating system allows, but it is recommended that they be short and descriptive of what the script is designed to do. It is also good practice to not have blank spaces in file names.

## Example script[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#example-script "Permanent link")

An example script might be a file called `tell_time.py` that contains:

```
<span></span><code><span class="sd">"""</span>
<span class="sd">A script to show the user the current time.</span>

<span class="sd">Author: Matthew Pitkin</span>
<span class="sd">Email: m.pitkin@lancaster.ac.uk</span>
<span class="sd">Date: 22/06/2020</span>
<span class="sd">"""</span>

<span class="c1"># import the required modules</span>
<span class="kn">import</span> <span class="nn">datetime</span>


<span class="k">def</span> <span class="nf">gettime</span><span class="p">():</span>
<span class="w">    </span><span class="sd">"""</span>
<span class="sd">    A function to return the current time.</span>

<span class="sd">    Returns</span>
<span class="sd">    -------</span>
<span class="sd">    tuple:</span>
<span class="sd">        A tuple containing the hour, minutes and seconds.</span>
<span class="sd">    """</span>

    <span class="n">now</span> <span class="o">=</span> <span class="n">datetime</span><span class="o">.</span><span class="n">datetime</span><span class="o">.</span><span class="n">now</span><span class="p">()</span>

    <span class="k">return</span> <span class="n">now</span><span class="o">.</span><span class="n">hour</span><span class="p">,</span> <span class="n">now</span><span class="o">.</span><span class="n">minute</span><span class="p">,</span> <span class="n">now</span><span class="o">.</span><span class="n">second</span> <span class="o">+</span> <span class="mf">1e-6</span> <span class="o">*</span> <span class="n">now</span><span class="o">.</span><span class="n">microsecond</span>

<span class="c1"># get the time</span>
<span class="n">hour</span><span class="p">,</span> <span class="n">minute</span><span class="p">,</span> <span class="n">seconds</span> <span class="o">=</span> <span class="n">gettime</span><span class="p">()</span>

<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">"The current time is </span><span class="si">{</span><span class="n">hour</span><span class="si">}</span><span class="s2">:</span><span class="si">{</span><span class="n">minute</span><span class="si">}</span><span class="s2">:</span><span class="si">{</span><span class="n">seconds</span><span class="si">}</span><span class="s2">"</span><span class="p">)</span>
</code>
```

### Script structure[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#script-structure "Permanent link")

The above script's structure is as follows:

1.  comment block (see [below](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#commenting-code)), held within opening and closing `"""`, describing the script;
2.  importing of required modules (see the tutorial on [importing modules](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-importing-modules/));
3.  defining any functions (see the tutorial on [functions](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-functions/));
4.  performing any required tasks (in this case getting the time);
5.  outputting any required information (in this case printing the time to the screen).

This is a useful basis in which to order your code. In reality modules can be imported, and functions defined, anywhere within a code, so long as it is before they are used (remember scripts are interpreted from start to finish, so you must define something before you use it).

### Commenting code[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#commenting-code "Permanent link")

In most programming languages you can place comments in your code. These are useful ways of including notes and information to describe what your code is doing and why.

Important

Comments are important! They allow other people (and future you!) to understand a code more easily rather than trying to have to interpret it themselves. Use comments liberally throughout your code.

In Python there are two ways to specify if a line contains a comment rather than code that you want to run (both of which are shown in the above [example](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#example-script)):

1.  Start a line with a hash `#`.
2.  Place text between opening and closing lines containing three quotation marks `"""` or three apostrophes `'''` (you can also define a [string](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#string) [variable](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#variable) using this syntax).

Any comment lines will be ignored by the Python interpreter when the file is run.

## Running a script[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#running-a-script "Permanent link")

The above [example](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#example-script) script can be run in a [terminal](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#terminal) using:

```
<span></span><code>python<span class="w"> </span>tell_time.py
</code>
```

If you write a script in _VS Code_ you do not need to open a terminal to run it. You can hit the green play button in the top right corner and it will automatically open a terminal and run the script for you.

Note

If you are using Linux or Mac you can start your scripts with the line:

```
<span></span><code><span class="ch">#!/usr/bin/env python3</span>
</code>
```

This is known as a ["shebang"](https://en.wikipedia.org/wiki/Shebang_(Unix)) and if you make your script executable, e.g., with `chmod u+x tell_time.py` you can then just run it in the terminal with `./tell_time.py`, rather than having to type `python tell_time.py`.

## Using functions from another script[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#using-functions-from-another-script "Permanent link")

As described in the [Importing Modules](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-importing-modules/) demonstration, any file with the `.py` extension is also a Python module. This means that you can import [variables](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#variable), [functions](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#function) or [classes](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#class) defined in one script into another.

For small projects with multiple scripts it is useful to keep them in the same directory so that you can import between them as needed. (The more advanced topic of "[packaging](https://github.com/mattpitkin/lancstro)" your project is beyond the scope of this course, although is a very useful thing to learn.)

For example, I could create a new script in the same directory as `tell_time.py` called `sydney_time.py` that contains:

```
<span></span><code><span class="sd">"""</span>
<span class="sd">A script to tell me the current time in Sydney, Australia.</span>

<span class="sd">Author: Matthew Pitkin</span>
<span class="sd">Email: m.pitkin@lancaster.ac.uk</span>
<span class="sd">Date: 22/06/2020</span>
<span class="sd">"""</span>

<span class="c1"># import gettime function from tell_time script/module</span>
<span class="kn">from</span> <span class="nn">tell_time</span> <span class="kn">import</span> <span class="n">gettime</span>

<span class="c1"># use gettime function from tell_time</span>
<span class="n">hour</span><span class="p">,</span> <span class="n">minute</span><span class="p">,</span> <span class="n">seconds</span> <span class="o">=</span> <span class="n">gettime</span><span class="p">()</span>

<span class="c1"># get the time in Sydney</span>
<span class="n">sydneyhour</span> <span class="o">=</span> <span class="p">(</span><span class="n">hour</span> <span class="o">+</span> <span class="mi">9</span><span class="p">)</span> <span class="o">%</span> <span class="mi">24</span>

<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">"The current time in Sydney is </span><span class="si">{</span><span class="n">sydneyhour</span><span class="si">}</span><span class="s2">:</span><span class="si">{</span><span class="n">minute</span><span class="si">}</span><span class="s2">:</span><span class="si">{</span><span class="n">seconds</span><span class="si">}</span><span class="s2">"</span><span class="p">)</span>
</code>
```

Important

If you import a whole script as a Python module, e.g., use

```
<span></span><code><span class="kn">import</span> <span class="nn">tell_time</span>
</code>
```

in the above example, then that script will get run during the import. So in that `tell_time` case the time will also get printed. This is sometimes what you want to achieve, but you may just want to import the script so that you can use specified functions, classes or variables. To make sure that parts of the script are _not_ run on import you could instead write `tell_time.py` as:

```
<span></span><code><span class="sd">"""</span>
<span class="sd">A script to show the user the current time.</span>

<span class="sd">Author: Matthew Pitkin</span>
<span class="sd">Email: m.pitkin@lancaster.ac.uk</span>
<span class="sd">Date: 22/06/2020</span>
<span class="sd">"""</span>

<span class="c1"># import the required modules</span>
<span class="kn">import</span> <span class="nn">datetime</span>


<span class="k">def</span> <span class="nf">gettime</span><span class="p">():</span>
<span class="w">    </span><span class="sd">"""</span>
<span class="sd">    A function to return the current time.</span>

<span class="sd">    Returns</span>
<span class="sd">    -------</span>
<span class="sd">    tuple:</span>
<span class="sd">        A tuple containing the hour, minutes and seconds.</span>
<span class="sd">    """</span>

    <span class="n">now</span> <span class="o">=</span> <span class="n">datetime</span><span class="o">.</span><span class="n">datetime</span><span class="o">.</span><span class="n">now</span><span class="p">()</span>

    <span class="k">return</span> <span class="n">now</span><span class="o">.</span><span class="n">hour</span><span class="p">,</span> <span class="n">now</span><span class="o">.</span><span class="n">minute</span><span class="p">,</span> <span class="n">now</span><span class="o">.</span><span class="n">second</span> <span class="o">+</span> <span class="mf">1e-6</span> <span class="o">*</span> <span class="n">now</span><span class="o">.</span><span class="n">microsecond</span>

<span class="c1"># anything within this if statement will not get run on import</span>
<span class="hll"><span class="k">if</span> <span class="vm">__name__</span> <span class="o">==</span> <span class="s2">"__main__"</span><span class="p">:</span>
</span>    <span class="c1"># get the time</span>
    <span class="n">hour</span><span class="p">,</span> <span class="n">minute</span><span class="p">,</span> <span class="n">seconds</span> <span class="o">=</span> <span class="n">gettime</span><span class="p">()</span>

    <span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">"The current time is </span><span class="si">{</span><span class="n">hour</span><span class="si">}</span><span class="s2">:</span><span class="si">{</span><span class="n">minute</span><span class="si">}</span><span class="s2">:</span><span class="si">{</span><span class="n">seconds</span><span class="si">}</span><span class="s2">"</span><span class="p">)</span>
</code>
```

Anything within the if statement `if __name__ == "__main__":` will only get run when running the script directly, but will not get run if importing the script as a module.

## Inputs[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#inputs "Permanent link")

A script can contain all the information that is required to run it (values that are defined within a script are sometimes referred to as being "hard-coded"). But often your script might require information from the user to provide it with data or tell it how it should run.

There are various ways that you can provide inputs to your script, which we will briefly mention below.

### Requesting input[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#requesting-input "Permanent link")

You can make a script request user input from the keyboard by using the [built-in](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#built-in) [`input`](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-built-in-functions/#input) function. `input` can take in a string as an [argument](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#argument), for example, a request for certain input to be provided, and then will take in whatever is written on the keyboard until the user presses Enter. This will then be assigned to a variable as a [string](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#string), e.g., after using:

```
<span></span><code><span class="n">name</span> <span class="o">=</span> <span class="nb">input</span><span class="p">(</span><span class="s2">"Enter your name: "</span><span class="p">)</span>
</code>
```

the `name` variable will contain whatever was entered. As the returned variable is always a string you may have to convert it if, for example, you want a number, e.g., convert an age to an integer number:

```
<span></span><code><span class="n">age</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="nb">input</span><span class="p">(</span><span class="s2">"Enter your age: "</span><span class="p">))</span>
</code>
```

### Inputs from a file[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#inputs-from-a-file "Permanent link")

A common and sensible way to take inputs is to read in data from a file. For more information on this see the tutorial on [reading files](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-io/).

### Command line arguments[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#command-line-arguments "Permanent link")

When you run a script from the [command line](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#command-line), i.e., by typing in the script name, you can pass it additional values (called command line arguments), that can then be used within the code, by writing them on the command line following the script's name. One way of using any additional command line arguments within your script is to use the [`sys`](https://docs.python.org/3/library/sys.html) standard module, in particular [`sys.argv`](https://docs.python.org/3/library/sys.html#sys.argv), which will list of all command line arguments as [strings](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#string) (including the script name as the first value in the list). As a very simple demonstration, if we had a script containing just:

```
<span></span><code><span class="c1"># import the sys module</span>
<span class="kn">import</span> <span class="nn">sys</span>

<span class="nb">print</span><span class="p">(</span><span class="n">sys</span><span class="o">.</span><span class="n">argv</span><span class="p">)</span>
</code>
```

and called it, say, `test.py`, then running it with some additional arguments gives:

```
<span></span><code>python<span class="w"> </span>test.py<span class="w"> </span><span class="m">1</span><span class="w"> </span>Hello<span class="w"> </span><span class="m">5</span>.6
<span class="o">[</span><span class="s1">'test.py'</span>,<span class="w"> </span><span class="s1">'1'</span>,<span class="w"> </span><span class="s1">'Hello'</span>,<span class="w"> </span><span class="s1">'5.6'</span><span class="o">]</span>
</code>
```

If we know the order that any command line arguments our code requires are going to be given, then we can extract the appropriate value from its position in the `argv` list and use it as required. For example, if we had the following script:

```
<span></span><code><span class="kn">import</span> <span class="nn">sys</span>

<span class="c1"># assume first name is the first command line argument (after the script name)</span>
<span class="n">firstname</span> <span class="o">=</span> <span class="n">sys</span><span class="o">.</span><span class="n">argv</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span>

<span class="c1"># assume surname is the second command line argument</span>
<span class="n">surname</span> <span class="o">=</span> <span class="n">sys</span><span class="o">.</span><span class="n">argv</span><span class="p">[</span><span class="mi">2</span><span class="p">]</span>

<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">"Your name is </span><span class="si">{</span><span class="n">firstname</span><span class="si">}</span><span class="s2"> </span><span class="si">{</span><span class="n">surname</span><span class="si">}</span><span class="s2">"</span><span class="p">)</span>
</code>
```

it assumes that there must be two arguments and that the user knows that the first one should be the first name and the second one should be the surname. If the user were to run (assuming this was in a script called `printname.py`):

```
<span></span><code>python<span class="w"> </span>printname.py<span class="w"> </span>Joe<span class="w"> </span>Bloggs
Your<span class="w"> </span>name<span class="w"> </span>is<span class="w"> </span>Joe<span class="w"> </span>Bloggs
</code>
```

then all is well. But, if there user ran:

```
<span></span><code>python<span class="w"> </span>printname.py<span class="w"> </span>Bloggs<span class="w"> </span>Joe
</code>
```

or

```
<span></span><code>python<span class="w"> </span>printname.py<span class="w"> </span>Joe
</code>
```

things would not work as expected.

Sometimes we might not want to have to give all the command line values, or we might not want to worry about having them in the correct order. The standard Python module [`argparse`](https://docs.python.org/3.8/howto/argparse.html#id1) can instead be used to provide more control over the command line inputs, for example, allowing named flags to specify inputs required. We will not go into detail of `argparse` here, except to show a very basic example (which we will assume is saved as a script called `person.py`):

```
<span></span><code tabindex="0"><span class="kn">import</span> <span class="nn">argparse</span>

<span class="c1"># create the parser (defining what command line arguments are expected)</span>
<span class="n">parser</span> <span class="o">=</span> <span class="n">argparse</span><span class="o">.</span><span class="n">ArgumentParser</span><span class="p">()</span>

<span class="c1"># add an argument called "name", which will require a --name flag followed by the input to be used </span>
<span class="n">parser</span><span class="o">.</span><span class="n">add_argument</span><span class="p">(</span><span class="s2">"--name"</span><span class="p">,</span> <span class="n">help</span><span class="o">=</span><span class="s2">"Enter your name"</span><span class="p">)</span>
<span class="n">parser</span><span class="o">.</span><span class="n">add_argument</span><span class="p">(</span><span class="s2">"--age"</span><span class="p">,</span> <span class="n">help</span><span class="o">=</span><span class="s2">"Enter your age"</span><span class="p">,</span> <span class="nb">type</span><span class="o">=</span><span class="nb">int</span><span class="p">)</span>  <span class="c1"># convert to integer</span>
<span class="n">parser</span><span class="o">.</span><span class="n">add_argument</span><span class="p">(</span><span class="s2">"--occupation"</span><span class="p">,</span> <span class="n">help</span><span class="o">=</span><span class="s2">"Enter your occupation"</span><span class="p">,</span> <span class="n">default</span><span class="o">=</span><span class="kc">None</span><span class="p">)</span>  <span class="c1"># default to None if not provided</span>

<span class="c1"># parse the command line arguments</span>
<span class="n">args</span> <span class="o">=</span> <span class="n">parser</span><span class="o">.</span><span class="n">parse_args</span><span class="p">()</span>

<span class="c1"># use the arguments</span>
<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">"</span><span class="si">{</span><span class="n">args</span><span class="o">.</span><span class="n">name</span><span class="si">}</span><span class="s2"> is </span><span class="si">{</span><span class="n">args</span><span class="o">.</span><span class="n">age</span><span class="si">}</span><span class="s2"> years old"</span><span class="p">)</span>
<span class="k">if</span> <span class="n">args</span><span class="o">.</span><span class="n">occupation</span> <span class="ow">is</span> <span class="ow">not</span> <span class="kc">None</span><span class="p">:</span>
    <span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">"</span><span class="si">{</span><span class="n">args</span><span class="o">.</span><span class="n">name</span><span class="si">}</span><span class="s2"> is a </span><span class="si">{</span><span class="n">args</span><span class="o">.</span><span class="n">occupation</span><span class="si">}</span><span class="s2">"</span><span class="p">)</span>
</code>
```

By default, when using `argparse`, if you give the script the `--help` argument it will print out the required arguments to screen given the information you provided to `help=` above:

```
<span></span><code>python<span class="w"> </span>person.py<span class="w"> </span>--help
usage:<span class="w"> </span>person.py<span class="w"> </span><span class="o">[</span>-h<span class="o">]</span><span class="w"> </span><span class="o">[</span>--name<span class="w"> </span>NAME<span class="o">]</span><span class="w"> </span><span class="o">[</span>--age<span class="w"> </span>AGE<span class="o">]</span><span class="w"> </span><span class="o">[</span>--occupation<span class="w"> </span>OCCUPATION<span class="o">]</span>

optional<span class="w"> </span>arguments:
<span class="w">  </span>-h,<span class="w"> </span>--help<span class="w">            </span>show<span class="w"> </span>this<span class="w"> </span><span class="nb">help</span><span class="w"> </span>message<span class="w"> </span>and<span class="w"> </span><span class="nb">exit</span>
<span class="w">  </span>--name<span class="w"> </span>NAME<span class="w">           </span>Enter<span class="w"> </span>your<span class="w"> </span>name
<span class="w">  </span>--age<span class="w"> </span>AGE<span class="w">             </span>Enter<span class="w"> </span>your<span class="w"> </span>age
<span class="w">  </span>--occupation<span class="w"> </span>OCCUPATION
<span class="w">                        </span>Enter<span class="w"> </span>your<span class="w"> </span>occupation
</code>
```

If we give it some inputs we get:

```
<span></span><code>python person.py --age 40 --name Matthew --occupation lecturer
Matthew is 40 years old
Matthew is a lecturer
</code>
```

Here, we see that by using these flags, it doesn't matter what order we enter the command line arguments.

## Outputs[¶](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//#outputs "Permanent link")

The simplest way for a Python script to output some information is to print that information to the screen for the user to see.

For this the [built-in](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#built-in) [`print`](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-built-in-functions/#print) function can be used. This function takes a [string](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../glossary/#string) and outputs it to the screen:

```
<span></span><code><span class="nb">print</span><span class="p">(</span><span class="s2">"Hello"</span><span class="p">)</span>
<span class="n">Hello</span>
</code>
```

This is useful for simple bits of information, but if your script is dealing with larger amounts of information then it is more useful to output it to a file (see the tutorial on [outputting to file](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-io/)), or to generate a plot (see the tutorial on [plotting](https://www.lancaster.ac.uk/staff/drummonn/PHYS281/demo-scripts//../demo-matplotlib/)).
