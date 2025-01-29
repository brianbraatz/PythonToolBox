---
Description: python - Is it better to have multiple files for scripts or just one large script file with every function? - Stack Overflow
Notes: I started a project about a year ago involving a simple terminal-based RPG with Python 3. Without really thinking about it I just jumped into it. I started with organizing multiple scripts for each..
author: The Gaming Hideout
        
            58422 gold badges1111 silver badges2727 bronze badges
Url: https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi
Created: "2025-01-28  09:46:29"
Modified: 
Tags:
---

# python - Is it better to have multiple files for scripts or just one large script file with every function? - Stack Overflow

source: https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi

> ## Excerpt
> I started a project about a year ago involving a simple terminal-based RPG with Python 3. Without really thinking about it I just jumped into it. I started with organizing multiple scripts for each..

---
# [Is it better to have multiple files for scripts or just one large script file with every function? \[closed\]](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi)

[Ask Question](https://stackoverflow.com/questions/ask)

Asked 6 years ago

Modified [3 years, 4 months ago](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi?lastactivity "2021-09-24 08:45:12Z")

Viewed 14k times

This question shows research effort; it is useful and clear

3

Save this question.

[](https://stackoverflow.com/posts/54349902/timeline)

Show activity on this post.

**Closed**. This question is [opinion-based](https://stackoverflow.com/help/closed-questions). It is not currently accepting answers.

___

**Want to improve this question?** Update the question so it can be answered with facts and citations by [editing this post](https://stackoverflow.com/posts/54349902/edit).

Closed 6 years ago.

[Improve this question](https://stackoverflow.com/posts/54349902/edit)

I started a project about a year ago involving a simple terminal-based RPG with Python 3. Without really thinking about it I just jumped into it. I started with organizing multiple scripts for each.. well, function. But halfway into the project, for the end goal I'm not sure if it's easier/more efficient to just have one very large script file or multiple files.

Since I'm using the `cmd` module for the terminal, I'm realizing getting the actual app running to be a looping game might be challenging with all these external files, but at the same time I have a `__init__.py` file to combine all the functions for the main run script. Here's the file structure.

[![File Structure](https://i.sstatic.net/ekyWO.png)](https://i.sstatic.net/ekyWO.png)

To clarify I'm not the greatest programmer, and I'm a novice in Python. I'm not sure of the compatibility issues yet with the `cmd` module.

So my question is this; **Should I keep this structure and it should work as intended?** Or should I combine all those `assets` scripts into one file? Or even put them apart of the start.py that uses `cmd`? Here's the start function, plus some snippets of various scripts.

# start.py

```
<span class="hljs-keyword">from</span> assets <span class="hljs-keyword">import</span> *
<span class="hljs-keyword">from</span> cmd <span class="hljs-keyword">import</span> Cmd
<span class="hljs-keyword">import</span> pickle
<span class="hljs-keyword">from</span> test <span class="hljs-keyword">import</span> TestFunction
<span class="hljs-keyword">import</span> time
<span class="hljs-keyword">import</span> sys
<span class="hljs-keyword">import</span> os.path
<span class="hljs-keyword">import</span> base64

<span class="hljs-keyword">class</span> <span class="hljs-title class_">Grimdawn</span>(<span class="hljs-title class_ inherited__">Cmd</span>):

    <span class="hljs-keyword">def</span> <span class="hljs-title function_">do_start</span>(<span class="hljs-params">self, args</span>):
        <span class="hljs-string">"""Start a new game with a brand new hero."""</span>
        <span class="hljs-comment">#fill</span>
    <span class="hljs-keyword">def</span> <span class="hljs-title function_">do_test</span>(<span class="hljs-params">self, args</span>):
        <span class="hljs-string">"""Run a test script. Requires dev password."""</span>
        password = <span class="hljs-built_in">str</span>(base64.b64decode(<span class="hljs-string">"N0tRMjAxIEJSRU5ORU1BTg=="</span>))
        <span class="hljs-keyword">if</span> <span class="hljs-built_in">len</span>(args) == <span class="hljs-number">0</span>:
            <span class="hljs-built_in">print</span>(<span class="hljs-string">"Please enter the password for accessing the test script."</span>)
        <span class="hljs-keyword">elif</span> args == password:
            test_args = <span class="hljs-built_in">input</span>(<span class="hljs-string">'&gt; Enter test command.\n&gt; '</span>)
            <span class="hljs-keyword">try</span>:
                TestFunction(test_args.upper())
            <span class="hljs-keyword">except</span> IndexError:
                <span class="hljs-built_in">print</span>(<span class="hljs-string">'Enter a command.'</span>)
        <span class="hljs-keyword">else</span>:
            <span class="hljs-built_in">print</span>(<span class="hljs-string">"Incorrect password."</span>)
    <span class="hljs-keyword">def</span> <span class="hljs-title function_">do_quit</span>(<span class="hljs-params">self, args</span>):
        <span class="hljs-string">"""Quits the program."""</span>
        <span class="hljs-built_in">print</span>(<span class="hljs-string">"Quitting."</span>)
        <span class="hljs-keyword">raise</span> SystemExit


<span class="hljs-keyword">if</span> __name__ == <span class="hljs-string">'__main__'</span>:

    prompt = Grimdawn()
    prompt.prompt = <span class="hljs-string">'&gt; '</span>
    <span class="hljs-comment">#ADD VERSION SCRIPT TO PULL VERSION FROM FOR PRINT</span>
    prompt.cmdloop(<span class="hljs-string">'Joshua B - Grimdawn v0.0.3 |'</span>)
```

# test.py

```
<span class="hljs-keyword">from</span> assets <span class="hljs-keyword">import</span> *
<span class="hljs-keyword">def</span> <span class="hljs-title function_">TestFunction</span>(<span class="hljs-params">args</span>):
    player1 = BaseCharacter()
    player2 = BerserkerCharacter(<span class="hljs-string">'Jon'</span>, <span class="hljs-string">'Snow'</span>)
    player3 = WarriorCharacter(<span class="hljs-string">'John'</span>, <span class="hljs-string">'Smith'</span>)
    player4 = ArcherCharacter(<span class="hljs-string">'Alexandra'</span>, <span class="hljs-string">'Bobampkins'</span>)
    shop = BaseShop()
    item = BaseItem()
    <span class="hljs-comment">#//fix this to look neater, maybe import switch case function</span>
    <span class="hljs-keyword">if</span> args == <span class="hljs-string">"BASE_OFFENSE"</span>:
        <span class="hljs-built_in">print</span>(<span class="hljs-string">'Base Character: Offensive\n-------------------------\n{}'</span>.<span class="hljs-built_in">format</span>(player1.show_player_stats(<span class="hljs-string">"offensive"</span>)))
        <span class="hljs-keyword">return</span>
    <span class="hljs-keyword">elif</span> args == <span class="hljs-string">"BASE_DEFENSE"</span>:
        <span class="hljs-built_in">print</span>(<span class="hljs-string">'Base Character: Defensive\n-------------------------\n{}'</span>.<span class="hljs-built_in">format</span>(player1.show_player_stats(<span class="hljs-string">"defensive"</span>)))
        <span class="hljs-keyword">return</span>

 *   *   *
```

# player.py

```
<span class="hljs-comment">#import functions used by script</span>
<span class="hljs-comment">#random is a math function used for creating random integers</span>
<span class="hljs-keyword">import</span> random
<span class="hljs-comment">#pickle is for saving/loading/writing/reading files</span>
<span class="hljs-keyword">import</span> pickle
<span class="hljs-comment">#sys is for system-related functions, such as quitting the program</span>
<span class="hljs-keyword">import</span> sys
<span class="hljs-comment">#create a class called BaseCharacter, aka an Object()</span>
<span class="hljs-keyword">class</span> <span class="hljs-title class_">BaseCharacter</span>:
    <span class="hljs-comment">#define what to do when the object is created, or when you call player = BaseCharacter()</span>
    <span class="hljs-keyword">def</span> <span class="hljs-title function_">__init__</span>(<span class="hljs-params">self</span>):
        <span class="hljs-comment">#generate all the stats. these are the default stats, not necessarily used by the final class when player starts to play.</span>
        <span class="hljs-comment">#round(random.randint(25,215) * 2.5) creates a random number between 25 and 215, multiplies it by 2.5, then roudns it to the nearest whole number</span>
        self.gold = <span class="hljs-built_in">round</span>(random.randint(<span class="hljs-number">25</span>, <span class="hljs-number">215</span>) * <span class="hljs-number">2.5</span>)
        self.currentHealth = <span class="hljs-number">100</span>
        self.maxHealth = <span class="hljs-number">100</span>
        self.stamina = <span class="hljs-number">10</span>
        self.resil = <span class="hljs-number">2</span>
        self.armor = <span class="hljs-number">20</span>
        self.strength = <span class="hljs-number">15</span>
        self.agility = <span class="hljs-number">10</span>
        self.criticalChance = <span class="hljs-number">25</span>
        self.spellPower = <span class="hljs-number">15</span>
        self.intellect = <span class="hljs-number">5</span>
        self.speed = <span class="hljs-number">5</span>
        self.first_name = <span class="hljs-string">'New'</span>
        self.last_name = <span class="hljs-string">'Player'</span>
        self.desc = <span class="hljs-string">"Base Description"</span>
        self.class_ = <span class="hljs-literal">None</span>
        self.equipment = [<span class="hljs-literal">None</span>] * <span class="hljs-number">6</span>
    <span class="hljs-comment">#define the function to update stats when the class is set</span>
    <span class="hljs-keyword">def</span> <span class="hljs-title function_">updateStats</span>(<span class="hljs-params">self, attrs, factors</span>):
        <span class="hljs-comment">#try to do a function</span>
        <span class="hljs-keyword">try</span>:
            <span class="hljs-comment">#iterate, or go through data</span>
            <span class="hljs-keyword">for</span> attr, fac <span class="hljs-keyword">in</span> <span class="hljs-built_in">zip</span>(attrs, factors):
                val = <span class="hljs-built_in">getattr</span>(self, attr)
                <span class="hljs-built_in">setattr</span>(self, attr, val * fac)
        <span class="hljs-comment">#except an error with a value given or not existing values</span>
        <span class="hljs-keyword">except</span>:
            <span class="hljs-keyword">raise</span>(<span class="hljs-string">"Error updating stats."</span>)
    <span class="hljs-comment">#print out the stats when called</span>
    <span class="hljs-comment">#adding the category line in between the ( ) makes it require a parameter when called</span>
    <span class="hljs-keyword">def</span> <span class="hljs-title function_">show_player_stats</span>(<span class="hljs-params">self, category</span>):
 *   *   *
```

# note

The purpose of the scripts is to show what kind of structure they have so it helps support the question of whether I should combine or not

-   [python](https://stackoverflow.com/questions/tagged/python "show questions tagged 'python'")
-   [python-3.x](https://stackoverflow.com/questions/tagged/python-3.x "show questions tagged 'python-3.x'")
-   [file](https://stackoverflow.com/questions/tagged/file "show questions tagged 'file'")
-   [directory-structure](https://stackoverflow.com/questions/tagged/directory-structure "show questions tagged 'directory-structure'")
-   [codeanywhere](https://stackoverflow.com/questions/tagged/codeanywhere "show questions tagged 'codeanywhere'")

[Share](https://stackoverflow.com/q/54349902 "Short permalink to this question")

Share a link to this question

Copy link[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/ "The current license for this post: CC BY-SA 4.0")

[Improve this question](https://stackoverflow.com/posts/54349902/edit)

Follow 

Follow this question to receive notifications

asked Jan 24, 2019 at 15:19

[

![The Gaming Hideout's user avatar](https://www.gravatar.com/avatar/9b9783e9dee6258e873fca92be481426?s=64&d=identicon&r=PG&f=y&so-version=2)

](https://stackoverflow.com/users/4524762/the-gaming-hideout)

[The Gaming Hideout](https://stackoverflow.com/users/4524762/the-gaming-hideout)The Gaming Hideout

58422 gold badges1111 silver badges2727 bronze badges

[Add a comment](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi# "Use comments to ask for more information or suggest improvements. Avoid answering questions in comments.")  | [](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi# "Expand to show all comments on this post")

## 4 Answers 4

Sorted by: [Reset to default](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi?answertab=scoredesc#tab-top)

Highest score (default) Trending (recent votes count more) Date modified (newest first) Date created (oldest first)

This answer is useful

10

Save this answer.

[](https://stackoverflow.com/posts/54350791/timeline)

Show activity on this post.

First a bit of terminology:

-   a "script" is python (.py) file that is intended to be directly executed (`python myscript.py`)
-   a "module" is a python file (usually containing mostly functions and classes definitions) that is intended to be imported by a script or another module.
-   a "package" is a directory eventually containing modules and (mandatory in py2, not in py3) an `__init__.py` file.

You can check the tutorial for more on modules and packages.

Basically, what you want is to organize your code in coherent units (packages / modules / scripts).

For a complete application, you will typically have a "main" module (doesn't have to be named "main.py" - actually it's often named as the application itself) that will only import some definitions (from the stdlib, from 3rd part libs and from your own modules), setup things and run the application's entry point. In your example that would be the "start.py" script.

For the remaining code, what you want is that each module has strong cohesion (functions and classes defined in it are closely related and concur to implement the same feature) and low coupling (each module is as independant as possible of other modules). You can technically put as much functions and classes as you want in a single module, but a too huge module can become a pain to maintain, so if after a first reorganisation based on high cohesion / low coupling you find yourself with a 5000+klocs module you'll probably want to turn it into a package with more specialized submodules.

If you still have a couple utilitie functions that clearly don't fit in any of your modules, the usual solution is to put them together in an "utils.py" (or "misc.py" or "helpers.py" etc) module.

Two things that you absolutely want to avoid are:

1.  circular dependencies, either direct (module A depends on module B, module B depends on module A) or indirect (module A depends on module B which depends on module A). If you find you have such case, it means you should either merge two modules together or extract some definitions to a third module.
    
2.  wildcard import ("from module import \*"), which are a major PITA wrt/ maintainability (you can't tell from the import where some names are imported from) and make the code subject to unexpected - and sometimes not obvious - breakage
    

As you can see, this is still quite very a generic guideline, but deciding what belongs together can not be automated and in the end depends on your own judgement.

[Share](https://stackoverflow.com/a/54350791 "Short permalink to this answer")

Share a link to this answer

Copy link[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/ "The current license for this post: CC BY-SA 4.0")

[Improve this answer](https://stackoverflow.com/posts/54350791/edit)

Follow 

Follow this answer to receive notifications

[edited Sep 24, 2021 at 8:45](https://stackoverflow.com/posts/54350791/revisions "show all edits to this post")

answered Jan 24, 2019 at 16:04

[

![bruno desthuilliers's user avatar](https://www.gravatar.com/avatar/e2c31ca37c09ab42763f690e0d1355d7?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/41316/bruno-desthuilliers)

[bruno desthuilliers](https://stackoverflow.com/users/41316/bruno-desthuilliers)bruno desthuilliers

77.9k66 gold badges9999 silver badges128128 bronze badges

[Add a comment](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi# "Use comments to ask for more information or suggest improvements. Avoid comments like “+1” or “thanks”.")  | [](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi# "Expand to show all comments on this post")

This answer is useful

4

Save this answer.

[](https://stackoverflow.com/posts/54350797/timeline)

Show activity on this post.

The way you have it currently is fine, personally I much prefer a lot of files as it's a lot easier to maintain. The main issue I see is that all of your code is going under `assets`, so either you'll end up with everything dumped there (defeating the point of calling it that), or you'll eventually end up with a bit of a mess of folders once you start coding other bits such as the world/levels and so on.

A quite common way of designing projects is your root would be `Grimdawn`, which contians one file to call your code, then all your actual code goes in `Grimdawn/grimdawn`. I would personally forget the `assets` folder and instead put everything at the root of that folder, and only go deeper if some of the files get more complex or could be grouped.

I would suggest something like this (put in a couple of additions as an example):

```
Grimdawn/characters/Jon_Snow
Grimdawn/characters/New_Player
Grimdawn/start.py
Grimdawn/grimdawn/utils/(files containing generic functions that are <span class="hljs-keyword">not</span> game specific)
Grimdawn/grimdawn/classes.py
Grimdawn/grimdawn/combat.py
Grimdawn/grimdawn/items.py
Grimdawn/grimdawn/mobs/generic.py
Grimdawn/grimdawn/mobs/bosses.py
Grimdawn/grimdawn/player.py
Grimdawn/grimdawn/quests/quest1.py
Grimdawn/grimdawn/quests/quest2.py
Grimdawn/grimdawn/shops.py
```

[Share](https://stackoverflow.com/a/54350797 "Short permalink to this answer")

Share a link to this answer

Copy link[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/ "The current license for this post: CC BY-SA 4.0")

[Improve this answer](https://stackoverflow.com/posts/54350797/edit)

Follow 

Follow this answer to receive notifications

answered Jan 24, 2019 at 16:04

[

![Peter's user avatar](https://www.gravatar.com/avatar/2303300fa4b29197c3a11eea331afdbf?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/2403000/peter)

[Peter](https://stackoverflow.com/users/2403000/peter)Peter

3,49533 gold badges3030 silver badges6565 bronze badges

[Add a comment](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi# "Use comments to ask for more information or suggest improvements. Avoid comments like “+1” or “thanks”.")  | [](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi# "Expand to show all comments on this post")

This answer is useful

1

Save this answer.

[](https://stackoverflow.com/posts/54350063/timeline)

Show activity on this post.

The pythonic approach to what goes into a single file (I'll discuss as it applies largely to classes) is that a single file is a **module** (not a package as I said previously).

A number of tools will typically exist in a single package, but all of the tools in a single module should remain centered around a single theme. With that said, a very small project I will typically keep in a single file with several functions and maybe a few classes inside. I would then use if main to contain the script as I want it run in its entirety.

```
<span class="hljs-keyword">if</span> __name__== <span class="hljs-string">'__main__'</span>: 
```

I would break logic down into functions as much as makes sense so that the main body of the script is readable as higher level logic.

Short answer: A file for every function is not manageable on any scale. You should put things together into files (modules) with related functionality. It is up to you as to whether the current functions should be clustered together into modules or not.

[Share](https://stackoverflow.com/a/54350063 "Short permalink to this answer")

Share a link to this answer

Copy link[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/ "The current license for this post: CC BY-SA 4.0")

[Improve this answer](https://stackoverflow.com/posts/54350063/edit)

Follow 

Follow this answer to receive notifications

[edited Jan 24, 2019 at 15:47](https://stackoverflow.com/posts/54350063/revisions "show all edits to this post")

answered Jan 24, 2019 at 15:26

[

![Xander YzWich's user avatar](https://i.sstatic.net/0YsPF.jpg?s=64)

](https://stackoverflow.com/users/2196988/xander-yzwich)

[Xander YzWich](https://stackoverflow.com/users/2196988/xander-yzwich)Xander YzWich

14111 silver badge1313 bronze badges

3

-   I think I understand with the theme idea, but other than that I guess I'm not sure how to use that answer.
    
    – [The Gaming Hideout](https://stackoverflow.com/users/4524762/the-gaming-hideout "584 reputation")
    
    [Commented Jan 24, 2019 at 15:29](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi#comment95515506_54350063)
    
-   @TheGamingHideout the answer is that it really depends on the project. Growth potential should be considered as to what type of things will go together. Every function doesn't need it's own file. I'll edit to make it more clear.
    
    – [Xander YzWich](https://stackoverflow.com/users/2196988/xander-yzwich "141 reputation")
    
    [Commented Jan 24, 2019 at 15:45](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi#comment95516132_54350063)
    
-   @XanderYzWich I totally agree, but in Python "module" and "package" are well-defined terms, so using one for the other can only confuse newcomers.
    
    – [bruno desthuilliers](https://stackoverflow.com/users/41316/bruno-desthuilliers "77,882 reputation")
    
    [Commented Jan 24, 2019 at 16:06](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi#comment95516993_54350063)
    

[Add a comment](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi# "Use comments to ask for more information or suggest improvements. Avoid comments like “+1” or “thanks”.")  | [](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi# "Expand to show all comments on this post")

This answer is useful

\-1

Save this answer.

[](https://stackoverflow.com/posts/54350337/timeline)

Show activity on this post.

There are several ways to approach organizing your code and it ultimately comes down to:

1.  Personal Preference
2.  Team coding standards for your Project
3.  Naming / Structure / Architecture Conventions for your Company

They way I organize my Python code is by creating several directories:

[![Folder Structure for Code Organization](https://i.sstatic.net/9keqL.png)](https://i.sstatic.net/9keqL.png)

-   class\_files (Reusable code)
-   input\_files (Files read by scripts)
-   output\_files (Files written by scripts)
-   scripts (Code executed)

This has served me pretty well. Import your paths relatively so the code can be run from any place it is cloned. Here's how I handle the imports in my script files:

```
<span class="hljs-keyword">import</span> sys
<span class="hljs-comment"># OS Compatibility for importing Class Files</span>
<span class="hljs-keyword">if</span>(sys.platform.lower().startswith(<span class="hljs-string">'linux'</span>)):
  sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../class_files/'</span>)
<span class="hljs-keyword">elif</span>(sys.platform.lower().startswith(<span class="hljs-string">'win'</span>)):
  sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\class_files\\'</span>)

<span class="hljs-keyword">from</span> some_class_file <span class="hljs-keyword">import</span> my_reusable_method
```

This approach also makes it possible to make your code run in various version of Python and your code can detect and import as necessary.

```
<span class="hljs-keyword">if</span>(sys.version.find(<span class="hljs-string">'3.4'</span>) == <span class="hljs-number">0</span>):
  <span class="hljs-keyword">if</span>(sys.platform.lower().startswith(<span class="hljs-string">'linux'</span>) <span class="hljs-keyword">or</span> sys.platform.lower().startswith(<span class="hljs-string">'mac'</span>)):
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python34/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python34/certifi/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python34/chardet/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python34/idna/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python34/requests/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python34/urllib3/'</span>)
    <span class="hljs-keyword">elif</span>(sys.platform.lower().startswith(<span class="hljs-string">'win'</span>)):
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python34\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python34\\certifi\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python34\\chardet\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python34\\idna\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python34\\requests\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python34\\urllib3\\'</span>)
    <span class="hljs-keyword">else</span>:
            <span class="hljs-built_in">print</span>(<span class="hljs-string">'OS '</span> + sys.platform + <span class="hljs-string">' is not supported'</span>)
<span class="hljs-keyword">elif</span>(sys.version.find(<span class="hljs-string">'2.6'</span>) == <span class="hljs-number">0</span>):
    <span class="hljs-keyword">if</span>(sys.platform.lower().startswith(<span class="hljs-string">'linux'</span>) <span class="hljs-keyword">or</span> sys.platform.lower().startswith(<span class="hljs-string">'mac'</span>)):
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python26/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python26/certifi/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python26/chardet/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python26/idna/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python26/requests/'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'../modules/Python26/urllib3/'</span>)
    <span class="hljs-keyword">elif</span>(sys.platform.lower().startswith(<span class="hljs-string">'win'</span>)):
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python26\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python26\\certifi\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python26\\chardet\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python26\\idna\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python26\\requests\\'</span>)
            sys.path.insert(<span class="hljs-number">0</span>,<span class="hljs-string">'..\\modules\\Python26\\urllib3\\'</span>)
    <span class="hljs-keyword">else</span>:
            <span class="hljs-built_in">print</span>(<span class="hljs-string">'OS '</span> + sys.platform + <span class="hljs-string">' is not supported'</span>)
<span class="hljs-keyword">else</span>:
    <span class="hljs-built_in">print</span>(<span class="hljs-string">"Your OS and Python Version combination is not yet supported"</span>)
```

[Share](https://stackoverflow.com/a/54350337 "Short permalink to this answer")

Share a link to this answer

Copy link[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/ "The current license for this post: CC BY-SA 4.0")

[Improve this answer](https://stackoverflow.com/posts/54350337/edit)

Follow 

Follow this answer to receive notifications

[edited Jan 24, 2019 at 16:31](https://stackoverflow.com/posts/54350337/revisions "show all edits to this post")

answered Jan 24, 2019 at 15:40

[

![Luke Brady's user avatar](https://i.sstatic.net/bOUkJ.jpg?s=64)

](https://stackoverflow.com/users/9156799/luke-brady)

[Luke Brady](https://stackoverflow.com/users/9156799/luke-brady)Luke Brady

18511 silver badge88 bronze badges

2

-   3
    
    I haven't voted it down, but I think it may be down to the `sys.path` bit. It's very unpythonic doing it that way, what happens if a user has Python 2.7, 3.6, 3.7, etc? Even if you hard code it all, then 3.8 comes out and your code breaks again. It'd be a lot better to just import the module, and tell the user they need to pip install the module. Editing the system path shouldn't need to be done at all from within a project :)
    
    – [Peter](https://stackoverflow.com/users/2403000/peter "3,495 reputation")
    
    [Commented Jan 24, 2019 at 16:43](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi#comment95518370_54350337)
    
-   Thanks @Peter for that feedback.
    
    – [Luke Brady](https://stackoverflow.com/users/9156799/luke-brady "185 reputation")
    
    [Commented Jan 24, 2019 at 17:00](https://stackoverflow.com/questions/54349902/is-it-better-to-have-multiple-files-for-scripts-or-just-one-large-script-file-wi#comment95518994_54350337)
