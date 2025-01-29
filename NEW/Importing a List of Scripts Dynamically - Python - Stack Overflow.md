---
Description: Importing a List of Scripts Dynamically - Python - Stack Overflow
Notes: Say I have N python files (each with a main function) in a file structure like so:
tools \
|_ tool_1.py
|_ tool_2.py
...
|_ tool_N.py

Furthermore, I have a data structure like so:
files = [
    {&...
author: Daniel
        
            3,52711 gold badge99 silver badges2626 bronze badges
Url: https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python
Created: "2025-01-28  09:47:21"
Modified: 
Tags:
---

# Importing a List of Scripts Dynamically - Python - Stack Overflow

source: https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python

> ## Excerpt
> Say I have N python files (each with a main function) in a file structure like so:
tools \
|_ tool_1.py
|_ tool_2.py
...
|_ tool_N.py

Furthermore, I have a data structure like so:
files = [
    {&...

---
# [Importing a List of Scripts Dynamically - Python](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python)

[Ask Question](https://stackoverflow.com/questions/ask)

Asked 3 years, 6 months ago

Modified [3 years, 6 months ago](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python?lastactivity "2021-07-11 06:41:29Z")

Viewed 825 times

This question shows research effort; it is useful and clear

2

Save this question.

[](https://stackoverflow.com/posts/68330639/timeline)

Show activity on this post.

Say I have N python files (each with a `main` function) in a file structure like so:

```
tools \
|_ tool_1.py
|_ tool_2.py
...
|_ tool_N.py
```

Furthermore, I have a data structure like so:

```
files = [
    {<span class="hljs-string">"path"</span>:<span class="hljs-string">"tools/tool_1.py"</span>, <span class="hljs-string">"alias"</span> : <span class="hljs-string">"tools__tool_1"</span>}
    {<span class="hljs-string">"path"</span>:<span class="hljs-string">"tools/tool_2.py"</span>, <span class="hljs-string">"alias"</span> : <span class="hljs-string">"tools__tool_2"</span>}
    ...
    {<span class="hljs-string">"path"</span>:<span class="hljs-string">"tools/tool_N.py"</span>, <span class="hljs-string">"alias"</span> : <span class="hljs-string">"tools__tool_N"</span>}
]
```

How can I dynamically import these files into a single python file? The number of tools will increase over time and manually adding a new line for each is not feasible.

So how can I convert this:

```
<span class="hljs-keyword">from</span> tools.tool_1 <span class="hljs-keyword">import</span> main <span class="hljs-keyword">as</span> tools__tool_1
<span class="hljs-keyword">from</span> tools.tool_2 <span class="hljs-keyword">import</span> main <span class="hljs-keyword">as</span> tools__tool_2
...
<span class="hljs-keyword">from</span> tools.tool_N <span class="hljs-keyword">import</span> main <span class="hljs-keyword">as</span> tools__tool_N
```

To this?

```
<span class="hljs-keyword">for</span> file <span class="hljs-keyword">in</span> files:
    <span class="hljs-keyword">from</span> file[<span class="hljs-string">"path"</span>] <span class="hljs-keyword">import</span> main <span class="hljs-keyword">as</span> file[<span class="hljs-string">"alias"</span>]
```

-   [python](https://stackoverflow.com/questions/tagged/python "show questions tagged 'python'")
-   [python-3.x](https://stackoverflow.com/questions/tagged/python-3.x "show questions tagged 'python-3.x'")
-   [python-import](https://stackoverflow.com/questions/tagged/python-import "show questions tagged 'python-import'")

[Share](https://stackoverflow.com/q/68330639 "Short permalink to this question")

Share a link to this question

Copy link[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/ "The current license for this post: CC BY-SA 4.0")

[Improve this question](https://stackoverflow.com/posts/68330639/edit)

Follow 

Follow this question to receive notifications

[edited Jul 11, 2021 at 6:41](https://stackoverflow.com/posts/68330639/revisions "show all edits to this post")

Daniel

asked Jul 10, 2021 at 18:39

[

![Daniel's user avatar](https://lh5.googleusercontent.com/-Wnetlg2YXYs/AAAAAAAAAAI/AAAAAAAAAAA/ACHi3rc1soZTf850D5qj9a20B-pqrST8ng/photo.jpg?sz=64)

](https://stackoverflow.com/users/12821675/daniel)

[Daniel](https://stackoverflow.com/users/12821675/daniel)Daniel

3,52711 gold badge99 silver badges2626 bronze badges

9

-   2
    
    The right way to do this is with [`importlib`](https://docs.python.org/3.9/library/importlib.html). For example, you can do `module = importlib.import_module(name)`. You can then do `file["alias"] = module.main`.
    
    – [Tom Karzes](https://stackoverflow.com/users/5460719/tom-karzes "24,052 reputation")
    
    [Commented Jul 10, 2021 at 18:50](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120763897_68330639)
    
-   Can you please clarify in an example?
    
    – [Daniel](https://stackoverflow.com/users/12821675/daniel "3,527 reputation")
    
    [Commented Jul 10, 2021 at 18:51](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120763911_68330639)
    
-   1
    
    Sure: `module = importlib.import_module("tool_1")` Then do `tools__tool_1 = module.main`. Repeat for the other modules.
    
    – [Tom Karzes](https://stackoverflow.com/users/5460719/tom-karzes "24,052 reputation")
    
    [Commented Jul 10, 2021 at 18:53](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120763941_68330639)
    
-   1
    
    Oh, sorry, you can store it in a dict. Start with: `module = importlib.import_module("tool_1")` just as before, but then: `file["tools__tool_1"] = module.main`. These are Python objects, so you can manipulate them as such.
    
    – [Tom Karzes](https://stackoverflow.com/users/5460719/tom-karzes "24,052 reputation")
    
    [Commented Jul 10, 2021 at 18:57](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120763980_68330639)
    
-   2
    
    I think you're implementing something with a poor design. Consider instead using some sort of plug-in system that _automatically_ imports all the Python files in a folder. See [How to import members of all modules within a package?](https://stackoverflow.com/questions/14426574/how-to-import-members-of-all-modules-within-a-package) for an example of what I mean.
    
    – [martineau](https://stackoverflow.com/users/355230/martineau "123,393 reputation")
    
    [Commented Jul 10, 2021 at 20:12](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120764804_68330639)
    

[](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python# "Use comments to ask for more information or suggest improvements. Avoid answering questions in comments.") |  [Show **4** more comments](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python# "Expand to show all comments on this post")

## 2 Answers 2

Sorted by: [Reset to default](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python?answertab=scoredesc#tab-top)

Highest score (default) Trending (recent votes count more) Date modified (newest first) Date created (oldest first)

This answer is useful

2

Save this answer.

[](https://stackoverflow.com/posts/68332227/timeline)

Show activity on this post.

Ok, first a couple of disclaimers: (1) Dynamically importing modules may or may not be what you actually need. I have done so myself, but in my case I had a library with like 100 different models, and a common driver that dynamically loaded one of those models depending on the command-line options I gave it. The main point is that I never needed more than one of them loaded at a time, so it made sense to load that one module dynamically.

And (2) I'm far from an expert at importing modules and packages, but I'm usually able to get it to do what I want.

That having been said, if you believe that dynamically importing modules is what you want, then this should work for you. Note that I tried to create a complete example for you:

```
<span class="hljs-keyword">import</span> importlib

files = [
    {<span class="hljs-string">"path"</span> : <span class="hljs-string">"tools.tool_1"</span>, <span class="hljs-string">"name"</span> : <span class="hljs-string">"tools__tool_1"</span>},
    {<span class="hljs-string">"path"</span> : <span class="hljs-string">"tools.tool_2"</span>, <span class="hljs-string">"name"</span> : <span class="hljs-string">"tools__tool_2"</span>},
    {<span class="hljs-string">"path"</span> : <span class="hljs-string">"tools.tool_3"</span>, <span class="hljs-string">"name"</span> : <span class="hljs-string">"tools__tool_3"</span>}
]

module_dict = {}
main_dict = {}

<span class="hljs-keyword">for</span> file_desc <span class="hljs-keyword">in</span> files:
    path = file_desc[<span class="hljs-string">"path"</span>]
    name = file_desc[<span class="hljs-string">"name"</span>]

    module = importlib.import_module(path)

    module_dict[name] = module
    main_dict[name] = module.main

main_dict[<span class="hljs-string">"tools__tool_1"</span>]()
```

In this example, there are three modules that all reside in the directory `tools`. The modules are `tool_1`, `tool_2`, and `tool_3`. They are imported and stored in dictionaries under the names `tools__tool_1`, etc. Note: You may be able to simply use `tool_1` etc. for these names, unless you need to qualify them with `tools__` because you want to load modules from other directories into the same dictionaries.

Note that none of these imports have any effect on your global namespace. The modules are imported as objects, and they (or their `main` functions) are stored only in the dictionaries.

In terms of what you need, I wasn't entirely sure what you wanted, so I created two dictionaries. The first is `module_dict`, which imports the entire modules. The second is `main_dict`, which simply contains the `main` function from each imported module, as described in the original post. Note that each module is only imported once. If you only need one of these dictionaries, it's simple enough to just remove the one you don't want.

Anyway, suppose you want to invoke `main` from `tools.tool_1`. You can do this from `main_dict` as follows:

```
    main_dict[<span class="hljs-string">"tools__tool_1"</span>]()
```

If you want to invoke it, or any other function, from `module_dict`, you can do:

```
    module_dict[<span class="hljs-string">"tools__tool_1"</span>].main()
```

You can basically access everything in a module from `module_dict`, but if you only want to access `main`, then you could just have `main_dict`.

Again, there is probably more here than you need, but I wasn't entirely certain how you intended to use this. If you only need one of the dictionaries, just get rid of the other.

[Share](https://stackoverflow.com/a/68332227 "Short permalink to this answer")

Share a link to this answer

Copy link[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/ "The current license for this post: CC BY-SA 4.0")

[Improve this answer](https://stackoverflow.com/posts/68332227/edit)

Follow 

Follow this answer to receive notifications

[edited Jul 10, 2021 at 23:28](https://stackoverflow.com/posts/68332227/revisions "show all edits to this post")

answered Jul 10, 2021 at 23:21

[

![Tom Karzes's user avatar](https://www.gravatar.com/avatar/5eac1437118cb7435812c64ac49e4603?s=64&d=identicon&r=PG&f=y&so-version=2)

](https://stackoverflow.com/users/5460719/tom-karzes)

[Tom Karzes](https://stackoverflow.com/users/5460719/tom-karzes)Tom Karzes

24.1k33 gold badges2626 silver badges4545 bronze badges

0

[Add a comment](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python# "Use comments to ask for more information or suggest improvements. Avoid comments like “+1” or “thanks”.")  | [](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python# "Expand to show all comments on this post")

This answer is useful

\-3

Save this answer.

[](https://stackoverflow.com/posts/68330681/timeline)

Show activity on this post.

You need to call exec() function. See sample below:

```
<span class="hljs-built_in">exec</span>(<span class="hljs-string">'from datetime import datetime'</span>)
<span class="hljs-built_in">print</span>(datetime.now())
```

So in your case it would be:

```
<span class="hljs-keyword">for</span> file <span class="hljs-keyword">in</span> files:
    <span class="hljs-built_in">exec</span>(<span class="hljs-string">f'from <span class="hljs-subst">{file[<span class="hljs-string">"path"</span>]}</span> import main as <span class="hljs-subst">{file[<span class="hljs-string">"alias"</span>]}</span>'</span>)
```

[Share](https://stackoverflow.com/a/68330681 "Short permalink to this answer")

Share a link to this answer

Copy link[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/ "The current license for this post: CC BY-SA 4.0")

[Improve this answer](https://stackoverflow.com/posts/68330681/edit)

Follow 

Follow this answer to receive notifications

[edited Jul 10, 2021 at 22:08](https://stackoverflow.com/posts/68330681/revisions "show all edits to this post")

answered Jul 10, 2021 at 18:46

[

![k-war's user avatar](https://www.gravatar.com/avatar/b6c82e52699fd1f5a9ee4ce5a5c1fd7a?s=64&d=identicon&r=PG&f=y&so-version=2)

](https://stackoverflow.com/users/4292155/k-war)

[k-war](https://stackoverflow.com/users/4292155/k-war)k-war

54733 silver badges1616 bronze badges

5

-   4
    
    Don't use `exec`. Use `importlib`, which was specifically created to do this.
    
    – [Tom Karzes](https://stackoverflow.com/users/5460719/tom-karzes "24,052 reputation")
    
    [Commented Jul 10, 2021 at 18:52](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120763925_68330681)
    
-   @k-war's solution is far more elegant and works as expected - whats the advantage of `importlib` over `exec`?
    
    – [Daniel](https://stackoverflow.com/users/12821675/daniel "3,527 reputation")
    
    [Commented Jul 10, 2021 at 19:03](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120764049_68330681)
    
-   2
    
    @Daniel Using `exec` is never elegant, and it requires you to create a command string rather than passing the arguments directly to `import_module`. Further, you have no direct control over the namespace if you use `exec` like this. As I said, experienced Python users use `importlib` for this. `exec` is basically a sledgehammer that beginning Python programmers use even though better solutions are usually available. Try to understand that `importlib` is _very easy_ to use, and in fact I showed you exactly how to adapt it to your needs. I guess you didn't understand.
    
    – [Tom Karzes](https://stackoverflow.com/users/5460719/tom-karzes "24,052 reputation")
    
    [Commented Jul 10, 2021 at 19:21](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120764266_68330681)
    
-   1
    
    A good analogy is using the deprecated `document.write` interface in javascript, as opposed to the DOM commands that replaced it. The DOM commands let you manipulate the HTML nodes directly, as opposed to attempting to insert source code into the running program. Similarly, the `importlib` interface in Python allows you to import modules directly, as opposed to trying to create Python source code as a string that is then dynamically executed. That's something you want to avoid unless there's absolutely no other way to do it. That doesn't apply in this case.
    
    – [Tom Karzes](https://stackoverflow.com/users/5460719/tom-karzes "24,052 reputation")
    
    [Commented Jul 10, 2021 at 19:26](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120764346_68330681)
    
-   @TomKarzes - thanks for your detailed comments - happy to accept your answer as the solution to my question if you post an example
    
    – [Daniel](https://stackoverflow.com/users/12821675/daniel "3,527 reputation")
    
    [Commented Jul 10, 2021 at 22:46](https://stackoverflow.com/questions/68330639/importing-a-list-of-scripts-dynamically-python#comment120766343_68330681)
