---
Description: Whats your favorite Python quirk?
Notes: Archived post. New comments cannot be posted and votes cannot be cast.
author: UpsetCabinet6755
Url: https://www.reddit.com/r/Python/comments/4oje6w/whats_your_favorite_python_quirk/
Created: "2025-01-28  09:36:28"
Modified: 
Tags:
---

# What's your favorite Python quirk? : r/Python

source: https://www.reddit.com/r/Python/comments/4oje6w/whats_your_favorite_python_quirk/

> ## Excerpt
> Archived post. New comments cannot be posted and votes cannot be cast.

---
# What's your favorite Python quirk?

By quirk I mean unusual or unexpected feature of the language.

For example, I'm no Python expert, but I recently read [here](http://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html) about putting else clauses on loops, which I thought was pretty neat and unexpected.

Archived post. New comments cannot be posted and votes cannot be cast.

Sort by:

Best

Open comment sort options

-   Best
    -   Top
    -   New
    -   Controversial
    -   Old
    -   Q&A
    

[](https://www.reddit.com/user/deadmilk/)

[deadmilk](https://www.reddit.com/user/deadmilk/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d5qli/) • Edited 9y ago

context managers with the `with` statement.

Suh good.

Also, did you know you can use this syntax?

```
with a() as A, b() as B, c() as C:
    A.fun()
    B.fun()
    C.fun()
```

Reply reply

[![u/bcs avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/bcs/)

[bcs](https://www.reddit.com/user/bcs/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d7wr8/)

There is nothing quirky about context managers. They might actually be perfect.

Reply reply

3 more replies

3 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d7wr8/)

[](https://www.reddit.com/user/AMorpork/)

[AMorpork](https://www.reddit.com/user/AMorpork/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4df007/)

I remember when I started getting seriously into Javascript, having known Python very well, I saw that JS had a `with` statement as well and got excited.

I was disabused of that excitement very quickly.

Reply reply

\[deleted\]

• 9y ago

Comment deleted by user

Reply reply

[](https://www.reddit.com/user/AMorpork/)

[AMorpork](https://www.reddit.com/user/AMorpork/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlded/)

It's one of the worst features of the language!

In javascript, there are objects. They are similar to dictionaries in python, and defined in much the same way:

```
var x = {a: 1, b: 2, c: 3};
```

Those keys can be accessed in the same way as in python (`x["a"]`), and also in dot-syntax (`x.a`). The `with` statement basically lets you forget both of those. So instead of doing:

```
x.c = x.a + x.b;
```

You could do

```
with (x) {
    c = a + b;
}
```

While that might look convenient, it's an evil little features with a bunch of downsides. I won't reiterate them all here, but it makes a lot of shit impossible to optimize and really makes things confusing. It's incredibly strongly discouraged by all responsible JS coders.

Reply reply

[![u/execrator avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_4.png)](https://www.reddit.com/user/execrator/)

[execrator](https://www.reddit.com/user/execrator/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dumd3/)

I ran a morning session teaching our JS developers how to Python. We started with a sort of language diff; Python has this feature and JS doesn't; JS has this and Python doesn't etc. When it came to `with`, the wording was something like "Python has the `with` keyword. There is no equivalent feature in JS, though there is a bug with the same name"

Reply reply[![u/pythoneeeer avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/pythoneeeer/)

[pythoneeeer](https://www.reddit.com/user/pythoneeeer/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlrod/)

In other words, it's just like the Pascal `with` statement, from 1970.

You have to think that if no other language designers put a feature in their language after a few decades, maybe there's a reason for that. Sometimes it's a good reason (like: it's really hard to implement, or: it makes optimization a bear), but probably not in this case.

Reply reply

[![u/Brian avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/Brian/)

[Brian](https://www.reddit.com/user/Brian/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4ek145/)

> You have to think that if no other language designers put a feature in their language

Visual basic has it, along with the already mentioned javascript.

Though the fact that _those_ particular two languages are the exception is probably stronger testimony against the idea than no languages doing it at all.

Reply reply 

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlrod/) 

2 more replies

2 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlded/) 

3 more replies

3 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4df007/)

[](https://www.reddit.com/user/be_bo_i_am_robot/)

[be\_bo\_i\_am\_robot](https://www.reddit.com/user/be_bo_i_am_robot/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d6nxb/)

I love this also!

Reply reply\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dr0sm/)

I just starting learning Python, is `with` roughly analogous to a `using` block in C#?

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dyjx6/)

`with` in Python allows you to avoid repeating setup/cleanup code very succinctly.

The simplest example is:

```
# this opens file for reading - equivalent to f = open('file', 'r')
with open('file', 'r') as f:
    data = f.read()

...
# as we have now fallen out of the context block, f.close() has been called for us already
# so now we don't have to remember to type that ourselves
```

It's very little work in most cases to do this for anything that has boilerplate setup/cleanup code. There are two basic ways to do it.

One is with a generator using contextlib:

```
import contextlib

@contextlib.contextmanager
def ctx_func():
    # do whatever setup first; in this example, I'll just instantiate a class called Thing
    thing = Thing()
    
    # whatever you yield here is what gets put into the "as ..." variable
    yield thing

    # code after yield does not run until the context block exits, so cleanup goes here
    thing.cleanup()
```

I typically wrap the yield in a try/finally so that the cleanup code is executed even if an exception is raised while in the context managed block, but that may not always be what you want.

The other way to make a context manager is to write a class `__enter__` and `__exit__` methods - as you would expect, `__enter__` is where your setup code goes, and `__exit__` is where your cleanup code goes.

There are other interesting (and in some cases more esoteric) examples in the [contextlib](https://docs.python.org/3/library/contextlib.html) docs.

Reply reply

3 more replies

3 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dyjx6/) 

4 more replies

4 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dr0sm/) 

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d5qli/)

[![u/spidyfan21 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/spidyfan21/)

[spidyfan21](https://www.reddit.com/user/spidyfan21/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d7u2e/) • Edited 9y ago

I'm a pretty big fan of using `type` in awful ways. Never in production code, but its a lot of fun to play around with.

**Example**:

```
&gt;&gt;&gt;Dog = type('Dog', (), {"woof": lambda self: print("Woof")})
&gt;&gt;&gt;a = Dog()
&gt;&gt;&gt;a.woof()
Woof
```

EDIT: Fixed it. Thanks [u/pythoneeeer](https://www.reddit.com/user/pythoneeeer/)

Reply reply

[![u/pythoneeeer avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/pythoneeeer/)

[pythoneeeer](https://www.reddit.com/user/pythoneeeer/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d9coi/)

Do you mean

```
Dog = type('Dog', (), {"woof": lambda self: print("Woof")})
```

What you typed just raises a NameError.

Reply reply

[![u/spidyfan21 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/spidyfan21/)

[spidyfan21](https://www.reddit.com/user/spidyfan21/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dg73n/)

Whoops.

Reply reply

[](https://www.reddit.com/user/AMorpork/)

[AMorpork](https://www.reddit.com/user/AMorpork/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dgchu/)

Woofs.

Reply reply

[![u/Eurynom0s avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/Eurynom0s/)

[Eurynom0s](https://www.reddit.com/user/Eurynom0s/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dqoc4/)

That's Worf to you, lady.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dgchu/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dg73n/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d9coi/)

[![u/Spfifle avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/Spfifle/)

[Spfifle](https://www.reddit.com/user/Spfifle/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dn8nj/) • Edited 9y ago

One day while typing

```
class blueTokenMaker(tokenMaker):
     token = blueToken
     def __init__(self):
         tokenMaker.__init__(self, self.token)
```

I decided it would be nice to save some effort and build these classes dynamically. And lo and behold classFactory was born. Then I got tired of typing

```
blueTokenMaker = classFactory(blueToken)
```

and figured it would be nice to save some effort and build these variables dynamically. And lo and behold the following line was born.

```
for token in tokens:
    globals()[token.name+"TokenMaker"] = classFactory(token)
```

Then I flipped to another file in the project and noticed pycharm was softly weeping as it painted everything red, so I rolled it back :(

Reply reply

[![u/Bunslow avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/Bunslow/)

[Bunslow](https://www.reddit.com/user/Bunslow/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dqe73/)

Ahahahaha this is great. I too understand the urge to abstract away any and all repetition, now matter how bad the replacement might be

Reply reply

[](https://www.reddit.com/user/teambob/)

[teambob](https://www.reddit.com/user/teambob/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4du5na/)

It's my job to be repetitive. My job. My job. Repetitiveness is my job! I am going to go out there tonight and give the best performance of my life. The best performance of your life? The best performance of my life.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dqe73/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dn8nj/)[![u/Sir_Harry_of_Kane avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/Sir_Harry_of_Kane/)

[Sir\_Harry\_of\_Kane](https://www.reddit.com/user/Sir_Harry_of_Kane/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dipq5/)

Awful ways indeed.

Reply reply 

2 more replies

2 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d7u2e/)

[![u/d4rch0n avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/d4rch0n/)

[d4rch0n](https://www.reddit.com/user/d4rch0n/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4da140/)

Pythonistamancer

I love and hate this, but local variables existing in the scope of a loop and outside.

```
def foo():
    for x in range(3):
        z = 1
    # both work
    print(x)
    print(z)
```

I hated it at first, but now it seems to allow some extra flexibility, and can even make debugging easier at some points (find out what the last value of x was when `break` was called). It's especially useful for searching, where you can just break when the current item meets the condition.

As long as you know that behavior, it's not bad. Weird coming from C languages though.

Reply reply

[![u/Cosmologicon avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/Cosmologicon/)

[Cosmologicon](https://www.reddit.com/user/Cosmologicon/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhlu9/)

Python's scoping gets a lot of flack, but honestly that always baffled me. I've never gotten a satisfactory explanation of why block scoping is better than function scoping.

"What if you want to use the same variable to mean different things in different blocks of a single function?" Stop wanting to do that. That's terrible style. You're going to cause bugs.

Reply reply

[![u/earthboundkid avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/earthboundkid/)

[earthboundkid](https://www.reddit.com/user/earthboundkid/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhyoj/)

The one case where it causes problems is creating a closure in a loop. The variable value will just end up being the last value, which is not intuitive.

Reply reply

10 more replies

10 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhyoj/)[![u/MereInterest avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/MereInterest/)

[MereInterest](https://www.reddit.com/user/MereInterest/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4drubx/)

In C++, it's largely due to RAII. Closing a scope calls the destructors and releases resources. Placing the end of a scope is then equivalent to closing the "with" block in python.

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4drubx/) 

2 more replies

2 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhlu9/)[![u/TankorSmash avatar](https://external-preview.redd.it/7AlpvErovtQ160o9FyIIdHCzfL2k-ejc982U6uPCuzI.png?width=64&height=64&crop=smart&auto=webp&s=cb9e90752e80e12e3fa221e17ad4d388267cf5e7)](https://www.reddit.com/user/TankorSmash/)

[TankorSmash](https://www.reddit.com/user/TankorSmash/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4drgde/)

That leak is fixing in v3, at least for comprehensions.

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4drgde/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4da140/)

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4ddd4z/)

I must say, magic methods. Those give you the ability to make your own DSL just by using objects that do special stuff with i.e. their \_\_lt\_\_ method. And best, in Python 3.5 we have a new operator that is not widely used (afaik, not at all in the builtin types): '@' for matrix multiplication. So just implement \_\_matmul\_\_ or \_\_rmatmul\_\_ in your class and use the '@' operator for calling that :) I guess itertools.product would be a good one to shortcut by using '@'.

Reply reply

[](https://www.reddit.com/user/synack/)

[synack](https://www.reddit.com/user/synack/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dezkr/)

List comprehensions are faster than their equivalent for loops.

Reply reply

[![u/ogmiche avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/ogmiche/)

[ogmiche](https://www.reddit.com/user/ogmiche/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dkfk5/)

Now this one is interesting I didn't know that

Reply reply

[![u/Bunslow avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/Bunslow/)

[Bunslow](https://www.reddit.com/user/Bunslow/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dqpo5/)

As is slicing (both reading and writing)

Reply reply

[](https://www.reddit.com/user/Cybersoaker/)

[Cybersoaker](https://www.reddit.com/user/Cybersoaker/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dvtou/)

how?

Reply reply

[![u/VerilyAMonkey avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/VerilyAMonkey/)

[VerilyAMonkey](https://www.reddit.com/user/VerilyAMonkey/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e0t1i/)

Because the list building can be done with close-to-the-metal C instead of actually using a real Python list object. Theoretically a clever interpreter might be able to make them the same speed for simple loops.

Reply reply 

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dvtou/)[![u/diceroll123 avatar](https://styles.redditmedia.com/t5_3kihn/styles/profileIcon_2y8r79q3h4l91.png?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=7a6148c35345dad20ef59f2c11c4af617f98a42c)](https://www.reddit.com/user/diceroll123/)

[diceroll123](https://www.reddit.com/user/diceroll123/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e06vz/)

List comprehensions are just more fun in general.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dezkr/)

[](https://www.reddit.com/user/theywouldnotstand/)

[theywouldnotstand](https://www.reddit.com/user/theywouldnotstand/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4digki/)

Magic methods:

```
class Paradox:

    def __lt__(self, other):
       return True

    def __le__(self, other):
        return True

    def __eq__(self, other):
       return True

    def __ge__(self, other):
       return True

    def __gt__(self, other):
        return True

a = Paradox()
b = Paradox()

a &lt; b
a &lt;= b
a == b
a &gt;= b
a &gt; b

b &lt; a
b &lt;= a
b == a
b &gt;= a
b &gt; a
```

Just one humorous abuse of magic methods I've come across. It really demonstrates the power and flexibility of the language.

Reply reply

[![u/Sinistersnare avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/Sinistersnare/)

[Sinistersnare](https://www.reddit.com/user/Sinistersnare/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dke2t/)

from knowledge import \* as karma

Its not abuse, as le, ge, etc. Are not mathematical operators, just operators sometimes used in math.

Reply reply

[](https://www.reddit.com/user/theywouldnotstand/)

[theywouldnotstand](https://www.reddit.com/user/theywouldnotstand/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dkrnw/) • Edited 9y ago

It's abuse in the sense that creating an object that behaves this way is very unlikely to be useful or practical (and may, in fact, be more harmful than helpful) in most situations.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dke2t/) 

7 more replies

7 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4digki/)

[![u/bcs avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/bcs/)

[bcs](https://www.reddit.com/user/bcs/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d7sjt/)

`for/else` loops. They read a little funny but they are exactly what you want to write searching loops.

Reply reply

[![u/d4rch0n avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/d4rch0n/)

[d4rch0n](https://www.reddit.com/user/d4rch0n/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d9jat/)

Pythonistamancer

I wish they used a keyword other than `else`, but yeah I actually love it too. It's just not obvious to many at first. And they probably should have picked something unique for try/except/else/finally too, like try/except/success/finally

Reply reply

[![u/poundcakejumpsuit avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_1.png)](https://www.reddit.com/user/poundcakejumpsuit/)

[poundcakejumpsuit](https://www.reddit.com/user/poundcakejumpsuit/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4ddoq5/)

Some SO post suggested saying "then" in your head, which I found to be a good tip when learning it.

Reply reply 

2 more replies

2 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d9jat/)

[](https://www.reddit.com/user/Asdayasman/)

[Asdayasman](https://www.reddit.com/user/Asdayasman/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4ddnfk/)

I will never not annotate these.

```
for _ in []:
    ...
else:  # nobreak
    ...

try:
    ...
except:
    ...
else:  # noexcept
    ...
```

Reply reply[](https://www.reddit.com/user/pydry/)

[pydry](https://www.reddit.com/user/pydry/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dahxa/)

I don't like this one. The intended behavior of "else" isn't particularly obvious.

Reply reply

[](https://www.reddit.com/user/theywouldnotstand/)

[theywouldnotstand](https://www.reddit.com/user/theywouldnotstand/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4di49q/)

`else` in `try` blocks is more intuitively obvious than what `finally` does:

```
try:
    # try to open a file
    somefile = open('somefile')
except (FileNotFoundError, OSError):
    # exit if there's trouble opening the file
    exit('Couldn't find the file!')
else:
    # otherwise read and output the file contents and exit
    contents = somefile.read()
    somefile.close()
    exit(contents)
finally:
    # Intuition suggests this shouldn't execute since both
    # above clauses contain exit calls. However this will
    # execute *before* either exit call can.
    print('Foobar')
```

For the record, I know that context managers would be more appropriate for file interaction. I designed this example for the sake of argument (so that it could include an `else` clause.)

Reply reply[![u/psi- avatar](https://styles.redditmedia.com/t5_3ko7d/styles/profileIcon_3vkd0apxfzl01.jpg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=e02f57c5a796d670e1bf905bdfe2b88b461a6e25)](https://www.reddit.com/user/psi-/)

[psi-](https://www.reddit.com/user/psi-/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfyjr/)

Yup. I've done python relatively much before 2006 so probably before that particular syntax and have done programming in C/C++/C# for at least 15+ years.

Without looking it up, I see these options:

-   executed when loop was not entered
    
-   executed after loop was executed (do we have access to loop named variable and it's last value?)
    

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfyjr/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dahxa/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d7sjt/)

[![u/deafmalice avatar](https://styles.redditmedia.com/t5_1qlml8/styles/profileIcon_tptuqu7httra1.jpeg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=9d368d4543c4955651c6cf0e66e7cca067c8bb05)](https://www.reddit.com/user/deafmalice/)

[deafmalice](https://www.reddit.com/user/deafmalice/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d1yp8/)

Having self as a required parameter on methods. It allows for very creative method calls (like calling the method from the class, instead of the object).

Also, it offers consistency. Whenever I look through C++/Java code I am always confused by the presence of object attribute access both with and without this. Never happens in Python

This is known to all pythonistas who have ever used classes, but no other language I know has that.

Reply reply

[![u/hovissimo avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_2.png)](https://www.reddit.com/user/hovissimo/)

[hovissimo](https://www.reddit.com/user/hovissimo/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d3s5o/)

Huh. I never thought of it as a language feature before. I always thought that the mandatory first argument to methods was some sort of leftover of internal routing that was accidentally exposed in ye olden dayes and then left for backwards compatibility.

But now that you've framed in that way I completely agree with you. IMO the consistency in method signatures is the most important part. (I think it's because I'm dumb, and I need lots of consistency in my code to not get distracted while working.)

Reply reply

[](https://www.reddit.com/user/be_bo_i_am_robot/)

[be\_bo\_i\_am\_robot](https://www.reddit.com/user/be_bo_i_am_robot/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d6mwo/)

Jeez, having lived in PHP land for a time, consistency in method signatures is so vastly underappreciated!

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dcczk/)

I agree with you. PHP inconsistency is a plague. But Python is not exactly perfectly-consistent too.

Reply reply

[![u/exhuma avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_1.png)](https://www.reddit.com/user/exhuma/)

[exhuma](https://www.reddit.com/user/exhuma/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4di91p/)

I hate that they didn't remove camel case of the unittest module (and logging) with python 3.... they had one chance...

Reply reply

[](https://www.reddit.com/user/tipsqueal/)

[tipsqueal](https://www.reddit.com/user/tipsqueal/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4djbfv/)

Pythonista

The last thing anyone wanted was to make the transition to 3 any harder.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4di91p/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dcczk/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d6mwo/)

[![u/ubernostrum avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/ubernostrum/)

[ubernostrum](https://www.reddit.com/user/ubernostrum/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4du4r4/)

yes, you can have a pony

More fun you can have:

```
&gt;&gt;&gt; def hello():
...     print("Hello, world!")
...
&gt;&gt;&gt; import types
&gt;&gt;&gt; types.FunctionType.__call__(hello)
Hello, world!
```

Reply reply[](https://www.reddit.com/user/nemec/)

[nemec](https://www.reddit.com/user/nemec/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dyq2m/)

NLP Enthusiast

The consistency in action:

```
&gt;&gt;&gt; class Test:
...     def __init__(self):
...             self.inner = "Hello"
...     def method(self, arg):
...             print(self.inner, arg)
... 
&gt;&gt;&gt; t = Test()
&gt;&gt;&gt; t.method("World")
Hello World
&gt;&gt;&gt; Test.method(t, "World")
Hello World
```

Reply reply 

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d3s5o/)

[![u/coriolinus avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/coriolinus/)

[coriolinus](https://www.reddit.com/user/coriolinus/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d4hkr/)

Rust does it like that also.

Reply reply

2 more replies

2 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d4hkr/)

[![u/i_ate_god avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_2.png)](https://www.reddit.com/user/i_ate_god/)

[i\_ate\_god](https://www.reddit.com/user/i_ate_god/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfrac/)

> Whenever I look through C++/Java code I am always confused by the presence of object attribute access both with and without this. Never happens in Python

While I can appreciate the confusion when "this" isn't there, I'm not sure I understand why you would be confused if "this" IS there and how it's more confusing than self?

Reply reply

[![u/deafmalice avatar](https://styles.redditmedia.com/t5_1qlml8/styles/profileIcon_tptuqu7httra1.jpeg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=9d368d4543c4955651c6cf0e66e7cca067c8bb05)](https://www.reddit.com/user/deafmalice/)

[deafmalice](https://www.reddit.com/user/deafmalice/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dgzqf/)

What I meant was when object attributes are used both with this and without it in the same method. I applaud anybody who's using this everywhere.

Reply reply

2 more replies

2 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dgzqf/)[![u/firetangent avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/firetangent/)

[firetangent](https://www.reddit.com/user/firetangent/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhmmo/)

When I see `somevar` in a Java method I'm never sure if it's a class member variable, or if it's local to the method. Consistently putting `this.somevar` for member variables would fix this and I don't understand why Java does not _require_ it - it's the sort of language where you expect it to enforce that sort of policy. Then I got a nice, modern IDE and they appear in different colors now, but the readability of `this.` or `self.` is still superior.

Reply reply

[![u/earthboundkid avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/earthboundkid/)

[earthboundkid](https://www.reddit.com/user/earthboundkid/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhu07/)

Swift has this same problem, which surprises me because it's so modern otherwise.

Reply reply 

10 more replies

10 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhmmo/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfrac/)

[![u/pythoneeeer avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/pythoneeeer/)

[pythoneeeer](https://www.reddit.com/user/pythoneeeer/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlv4b/)

Languages with multiple dispatch do this, naturally.

Not only is the first parameter not special, but methods don't even 'belong to' classes, like they do in single dispatch languages.

Reply reply[![u/PcBoy111 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/PcBoy111/)

[PcBoy111](https://www.reddit.com/user/PcBoy111/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4duw2r/) • Edited 9y ago

Lua does this for class like tables, stuff like:

```
function Point:set(x, y)
    self.x = x or 0  
    self.y = y or 0  
end
```

`function Point:set(x, y)` is equivalent to `function Point.set(self, x, y)`

Reply reply 

13 more replies

13 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d1yp8/)

[![u/wnoise avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_2.png)](https://www.reddit.com/user/wnoise/)

[wnoise](https://www.reddit.com/user/wnoise/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4douyj/)

"Interval comparison". It lets you chain range checks: "a < b < c" is equivalent to "a < b and b < c".

Reply reply

[![u/CantankerousMind avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/CantankerousMind/)

[CantankerousMind](https://www.reddit.com/user/CantankerousMind/)

![Cake icon](https://www.redditstatic.com/shreddit/assets/illustrations/cake-day.svg) • [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfelw/)

Being able to assign a value to a variable using `if` and `else` on the same line. Basically a ternary operator:

```
x = str(x) if type(x) != str else x
```

I use ternary operators all the time in PHP, and only recently realized you could do the same in python. Not so much a quirk as it is convenient.

Also, assigning multiple variables on a single line:

```
city, state = "Denver", "CO"
```

or unpacking them:

```
location = ['Denver', 'CO']
city, state = location
```

Once again, none of these are really quirks. Just fun features that might not be super well known(or at least I assume they aren't because I don't see them being used very much).

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfelw/)

[](https://www.reddit.com/user/jcdyer3/)

[jcdyer3](https://www.reddit.com/user/jcdyer3/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4df0bb/)

`__class__` is just an attribute on an instance. You can reassign it however you like. Not something I would ever want to do in production code, but allows for some fun hacks.

Reply reply

[![u/nevus_bock avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/nevus_bock/)

[nevus\_bock](https://www.reddit.com/user/nevus_bock/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dyuvv/)

> _"Actually the type of an object may be changed by merely assigning a different class to its_ _**class**_ _attribute, but that is pure evil and I regret writing this footnote."_

> \- Luciano Ramalho: Fluent Python, p.242

Reply reply[](https://www.reddit.com/user/nemec/)

[nemec](https://www.reddit.com/user/nemec/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dzbk2/)

NLP Enthusiast

Hah, that's pretty funny.

```
&gt;&gt;&gt; class A:
...     def func(self):
...             print("A")
... 
&gt;&gt;&gt; class B:
...     def func(self):
...             print("B")
... 
&gt;&gt;&gt; a = A()
&gt;&gt;&gt; a.func()
A
&gt;&gt;&gt; a.__class__ = B
&gt;&gt;&gt; a.func()
B
```

Reply reply 

3 more replies

3 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4df0bb/)

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d791d/)

Tuple unpacking in function arguments:

```
X = lambda (a, (b, c)): a + b * c
print map(X, [(1, (2, 3)), (4, (5, 6))])
```

Sadly it went out in py3.

Reply reply

\[deleted\]

• 9y ago

Comment deleted by user

Reply reply

6 more replies

6 more replies

7 more replies

7 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d791d/)

[![u/dannypandy avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/dannypandy/)

[dannypandy](https://www.reddit.com/user/dannypandy/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4deuty/)

How about a least favorite quirk. Exponentiation is not `a^b`(as in most mathematical writing) its `a**b`. I can't tell you how many times this has killed me. (I switch between multiple languages constantly)

Though python is still by **far** my favorite language. So pretty.

**Edit**: reddit ate my caret, fixed

Reply reply

[![u/taleinat avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/taleinat/)

[taleinat](https://www.reddit.com/user/taleinat/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfat9/)

To be fair, `^` is the bitwise xor operator in many languages. For many programmers having it mean exponentiation would be confusing.

Reply reply

[![u/dannypandy avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/dannypandy/)

[dannypandy](https://www.reddit.com/user/dannypandy/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dh6yj/)

True, like a lot of things, this depends on your perspective (primarily programmer vs primarily mathematician).

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dh6yj/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfat9/)[![u/Ran4 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_2.png)](https://www.reddit.com/user/Ran4/)

[Ran4](https://www.reddit.com/user/Ran4/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dj62q/)

^ is a lot more annoying to type than \*\* on keyboards where ^ is a dead key, so I'm real happy about it.

Reply reply

[![u/Sean1708 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/Sean1708/)

[Sean1708](https://www.reddit.com/user/Sean1708/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dk3ni/)

Dead key?

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dm045/)

Depending on your keyboard language/layout, some characters behave differently. For example, ^ is an circumflex accent used in Portuguese. These characters behave differently in those layouts: press the dead key and then a letter to apply the accent to that letter (given that is a valid application of the accent).

Dead keys: [https://en.wikipedia.org/wiki/Dead\_key](https://en.wikipedia.org/wiki/Dead_key)

Circumflex accent: [https://en.wikipedia.org/wiki/Circumflex](https://en.wikipedia.org/wiki/Circumflex)

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dm045/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dk3ni/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dj62q/) 

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4deuty/)

[![u/zer01 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_1.png)](https://www.reddit.com/user/zer01/)

[zer01](https://www.reddit.com/user/zer01/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dk62g/)

In python 2.7 `True` and `False` are mutable.

```
In [1]: True = False

In [2]: if not True:
   ...:     print "Why aren't True/False immutable in 2.7?!"
   ...:
Why aren't True/False immutable in 2.7?!
```

I'm just waiting for someone to slip the following into a widely used package and watch the world burn, Joker style.

```
True, False = False, True
```

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dxl93/)

Do that to packages which people refuse to upgrade to python3. That'll teach them :P

Reply reply 

2 more replies

2 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dk62g/)

[](https://www.reddit.com/user/NelsonMinar/)

[NelsonMinar](https://www.reddit.com/user/NelsonMinar/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4deo1v/)

The use of `_` to mean "thing we don't care about". Ie

```
name, _, gender = 'Nelson,FOO,M'.split(',')
```

Reply reply

[](https://www.reddit.com/user/dacjames/)

[dacjames](https://www.reddit.com/user/dacjames/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dg574/)

from reddit import knowledge

That is a nice convention, but it is only a convention. Python treats `_` like any other identifier.

Reply reply

\[deleted\]

• 9y ago

Comment deleted by user

Reply reply

3 more replies

3 more replies

2 more replies

2 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dg574/)\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4df0xv/)

This is helpful if you use a linter. Linter will complain if you assign a variable then don't use it. But it won't complain about \_ being unused.

But watch out if you're using Django, because it encourages this:

```
from django.utils.translation import ugettext as _
```

Reply reply

[![u/usinglinux avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/usinglinux/)

[usinglinux](https://www.reddit.com/user/usinglinux/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dfcn7/)

`_` goes for any gettext, actually; django just follows the gettext convention.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4df0xv/) 

4 more replies

4 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4deo1v/)

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dxu8m/)

Python has a few quirks that are pretty interesting. I did a talk about this recently so I've still got a few on my mind.

Python caches the integers -5 to 256 as singletons. So, using the identity operator, we get some funny quirks.

```
&gt;&gt;&gt; 1000 is 1000
True
&gt;&gt;&gt; 4 is 4
True
&gt;&gt;&gt; 4 is 2*2
True
&gt;&gt;&gt; 1000 is 10*100
False
```

Wait, what?

There's also something interesting in the way Python does imports. Python's import mechanism, as far as CPython goes, lives in two places: `importlib.__import__` and `__builtins__.__import__`. The first is in the `importlib` module and the second is set up in all module scopes by the interpreter automatically. You can, interestingly enough, edit the import mechanism or remove it entirely.

```
&gt;&gt;&gt; import random #this works
&gt;&gt;&gt; del __builtins__.__import__
&gt;&gt;&gt; import os
ImportError: __import__ not found
```

Don't worry, you can fix this by setting `__builtins__.__import__ = importlib.__import__`. We just need to get our hands on the proper function...

```
&gt;&gt;&gt; from importlib import __import__
ImportError: __import__ not found
```

Oh wait, no you can't. (Unless you pre-imported `importlib`)

Ok, I've got one last one. Python keeps all default parameter values in a closure for each function. That's why it's convention to set default values as `None`.

```
&gt;&gt;&gt; def thing(arg=[]):
...    arg.append(1)
...    print(arg)
&gt;&gt;&gt; thing()
[1]
&gt;&gt;&gt; thing()
[1, 1]
&gt;&gt;&gt; thing()
[1, 1, 1]
&gt;&gt;&gt; thing()
[1, 1, 1, 1]
```

Reply reply

3 more replies

3 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dxu8m/)

[![u/rr1pp3rr avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/rr1pp3rr/)

[rr1pp3rr](https://www.reddit.com/user/rr1pp3rr/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d972o/) • Edited 9y ago

How flexible the magic method system makes your code. The best example I can think of for this is a [pandas Dataframe](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html).

[Here is an example (look at the part labelled "Accessing via label slices")](http://pandas.pydata.org/pandas-docs/stable/indexing.html#selection-by-label)

Pandas kind of abuses Python magic methods to the point where it almost doesn't look like python code at all. Specifically what they do with the index fields is crazy.

This type of coding can get out of hand real quick, and I would actually prefer if everything was just done using methods. I think they have methods for all of those functions, but they also overwrite the magic methods to expose that interface elsewhere.

It's very expressive, but makes the code a little hard to read.

Reply reply

[](https://www.reddit.com/user/Asdayasman/)

[Asdayasman](https://www.reddit.com/user/Asdayasman/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4ddqw1/)

I wouldn't trade it for the world. Being able to do `game_area[5, 10]` is so intuitively perfect.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d972o/)

[](https://www.reddit.com/user/red_hare/)

[red\_hare](https://www.reddit.com/user/red_hare/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e1ybt/)

Namedtuples, while seemingly innocent, are essentially a macro in Python.

The source code istruely terrifying.

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e1ybt/)

[![u/fatterSurfer avatar](https://styles.redditmedia.com/t5_ctt4b/styles/profileIcon_s0cnl2naxqt61.jpg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=055ae36b88ec01b2811f15bf107f74a959b96d0e)](https://www.reddit.com/user/fatterSurfer/)

[fatterSurfer](https://www.reddit.com/user/fatterSurfer/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d82jh/)

[Late binding closures](http://stackoverflow.com/questions/233673/lexical-closures-in-python). Basically, when you have a function that refers to an outside scope, it waits until function execution to look up the reference.

This is a really common "oops" when dealing with function generators (so common that it's in the [gotchas](http://docs.python-guide.org/en/latest/writing/gotchas/)), but I really love them, because outside of that context they are incredibly powerful.

On a similar note, using one-time evaluation of default arguments in functions to memoize them. Since default arguments are evaluated exactly once at function definition time, you can use them for memoization. They're also the standard workaround for when you want early binding closures, like when you're writing a function generator.

And finally, callable classes, and really all of the magic/dunder (double underscore) methods. Being able to override stuff like that is so profoundly powerful. Even things as simple as defining `__hash__` so you can use a user class as a dictionary key is fantastic.

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlxwj/)

Functions are objects.

```
def x(y, z):
    return y(z)
```

Reply reply

[![u/coderanger avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/coderanger/)

[coderanger](https://www.reddit.com/user/coderanger/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dztyf/)

Mucking with `__code__` (`func_code` in Python 2) is fun.

```
&gt;&gt;&gt; def myfunc(x):
          return x
&gt;&gt;&gt; myfunc.__code__ = (lambda x: x+1).__code__
&gt;&gt;&gt; myfunc(1)
2
```

This is nice because it lets you replace the content of a method without disturbing its scope, access to closure variables, etc.

Reply reply

3 more replies

3 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dztyf/)

[![u/not_perfect_yet avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/not_perfect_yet/)

[not\_perfect\_yet](https://www.reddit.com/user/not_perfect_yet/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dacld/)

I love that referencing an instance in the the object definition is not a keyword:

```
class huh:
    def __init__(neat,x,y,z=1):
        neat.x=x
        neat.y=y
        neat.z=z
```

is perfectly valid. In C++ it's "this" I think and that's a fixed keyword.

This just a neat little thing, from a functionality point of view, being able to redefine classes on the fly, adding or removing attributes or methods **at runtime** is a killer feature. Requires a bit of meta wizardry though.

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlvla/)

You should never, ever use something else than "self". It's not "pythonic", and is confusing for other defs.

Reply reply

[![u/f0nt4 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/f0nt4/)

[f0nt4](https://www.reddit.com/user/f0nt4/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dtlb3/)

tell this to the standard library:

```
def update(*args, **kwds):
    ...
    self, *args = args
```

[collection.MutableMapping](https://hg.python.org/cpython/file/3.5/Lib/_collections_abc.py)

Reply reply

[![u/epsy avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/epsy/)

[epsy](https://www.reddit.com/user/epsy/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e80ip/)

The reason for this is for `d.update(self=42)` to assign to `kwds` rather than collide with the `self` that means "the current object". No other way to properly do this. I should point out that they do use the correct name anyway though.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dtlb3/) 

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlvla/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dacld/)

[](https://www.reddit.com/user/Salyangoz/)

[Salyangoz](https://www.reddit.com/user/Salyangoz/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dg3s4/)

I like that empty lists and dictionaries are also considered as a `False` in `if` checks.

```
empty_dict = {}
empty_list = []
if not (empty_dict and empty_list):
    print 'Thats an empty dict'
Thats an empty dict
```

Reply reply

3 more replies

3 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dg3s4/)

[![u/iEvilMango avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/iEvilMango/)

[iEvilMango](https://www.reddit.com/user/iEvilMango/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dbxha/) • Edited 9y ago

It's probably pretty obvious, but everything being a variable makes writing object oriented programs really nice. For example, when writing a basic text adventure game to learn the language, I was trying to think about how to easily instantiate different characters or items, that I had as subclasses. I just guesses that I could do a dictionary of strings to objects and it worked, and that little thing just made me happy.

Reply reply

\[deleted\]

• 9y ago

Comment deleted by user

Reply reply

[![u/deafmalice avatar](https://styles.redditmedia.com/t5_1qlml8/styles/profileIcon_tptuqu7httra1.jpeg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=9d368d4543c4955651c6cf0e66e7cca067c8bb05)](https://www.reddit.com/user/deafmalice/)

[deafmalice](https://www.reddit.com/user/deafmalice/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhcsy/)

This is one thing I really dislike about Python. I get that bool is a subtype of int, but True being equal to 1 irks me.

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dhcsy/)

[![u/nab00 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/nab00/)

[nab00](https://www.reddit.com/user/nab00/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dp2jh/)

Python **float** type is equivalent to C **double**. This always confuses me as I am used to C notation where float is 4-byte long and double is 8 bytes.

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dp2jh/)

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dppi5/)

Else on loops to me is an anti pattern. To me it's really not obvious what the control flow is meant to be. I find it easier just to handle that behaviour more explicitly. Just my opinion.

Reply reply

3 more replies

3 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dppi5/)

[](https://www.reddit.com/user/pydry/)

[pydry](https://www.reddit.com/user/pydry/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dijqc/)

How the core modules are almost universally terrible.

If urllib2 just had a mediocre API rather than a gut wrenchingly horrible one we might not have requests.

Reply reply

[](https://www.reddit.com/user/James_Johnson/)

[James\_Johnson](https://www.reddit.com/user/James_Johnson/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlwo5/)

> How the core modules are almost universally terrible.

See: datetime

Reply reply

[![u/ebrious avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/ebrious/)

[ebrious](https://www.reddit.com/user/ebrious/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dq38l/)

Uhg this one is the worst for me. Urllib objects usually don't find their way into function signatures, datetime objects do all the time and its horrible how handicapped they are.

Reply reply 

6 more replies

6 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dlwo5/)[![u/Sir_Harry_of_Kane avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_5.png)](https://www.reddit.com/user/Sir_Harry_of_Kane/)

[Sir\_Harry\_of\_Kane](https://www.reddit.com/user/Sir_Harry_of_Kane/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dj34v/)

I don't agree with your statement about all core modules, but I do agree with you on urllib2.

It's like they thought, how can we take a beautiful, simple and yet expressive language and write a module that is ugly, complex and yet not expressive.

At what point does requests just become the urllib3 module?

Reply reply

[](https://www.reddit.com/user/pydry/)

[pydry](https://www.reddit.com/user/pydry/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4djlwn/)

> I don't agree with your statement about all core modules, but I do agree with you on urllib2.

I think for maybe 80-90% there's a better equivalent on pypi.

> It's like they thought, how can we take a beautiful, simple and yet expressive language and write a module that is ugly, complex and yet not expressive.

urllib2 is the kind of API you come up with when you're thinking about what the module does rather than how it will be used.

I've created some similar botched jobs before.

Unfortunately once an API gets wide usage it gets stuck.

> At what point does requests just become the urllib3 module?

Never. That's in the FAQ on the website.

Reply reply 

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dj34v/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dijqc/)

[![u/evolutionof avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/evolutionof/)

[evolutionof](https://www.reddit.com/user/evolutionof/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d41d9/)

`x > 5 and "your mom"` will evaluate to `False` if x <= 5, and `"your mom"` otherwise.

Not going to say that it is my favorite, but it is a little known quirk.

Reply reply

[![u/cymrow avatar](https://styles.redditmedia.com/t5_20ukn2/styles/profileIcon_zk73dyu4qty51.jpg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=52b46da8890030497d9fc525e8f58e685e34f992)](https://www.reddit.com/user/cymrow/)

[cymrow](https://www.reddit.com/user/cymrow/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d7p83/)

don't thread on me 🐍

Works with `or` too. It's a great shortcut if you can be reasonably sure that anyone who reads your code will understand it.

Instead of:

```
if val:
    x = val
else:
    x = 'default'
```

or:

```
x = val if val else 'default'
```

it's nice to just do:

```
x = val or 'default'
```

I use it all the time for function argument defaults. It protects against Python's mutable default argument quirk, and also allows users to pass in `None` when they explicitly want to use the default, even if they don't know what the default is.

```
def func(a_list=None):
    a_list = a_list or []
```

Reply reply

6 more replies

6 more replies

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d7p83/)

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dpcs3/)

It's a quirk, but makes sense if you know what's going on. `and` returns the right most value unless any values left if it are falsy. `or` returns the first truthy value or the right most value if none are truthy. Conditional expressions are evaluate the returned value as a boolean.

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dpcs3/)[![u/jceyes avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/jceyes/)

[jceyes](https://www.reddit.com/user/jceyes/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e6h8t/)

I like it too, and use it pretty heavily, but this kind of short circuit evaluation is not at all unique to python.

Reply reply [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d41d9/)

[![u/Why_is_that avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/Why_is_that/)

[Why\_is\_that](https://www.reddit.com/user/Why_is_that/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dt9am/)

Wow. I am thirty and I just realized I am so old that the quirks I know from python are slowly being removed.

My favorite quirk in python use to be the fact that you could declare the following

```
a = [1,2,3,a]
```

I have no idea what you would call this (a self-reflecting array) or how you use it but at a time (and I don't know when they nerfed it), this functions pretty much as you would expect it. You could go to a\[3\] and see the exact same structure and reference a\[3\]\[0\], a\[3\]\[1\], etc. You could go down that rabbit hole so far, that I never went all the way down to see how it was exactly limited or even more peculiar what it actually translated into (was it eating up memory or was it actually just the 4 bits of data I asked for, the 4th being a reference to the self).

Anyways, now if you try this you get an error that a is not referenced. This appears to be both python2.7 and python3. I am unsure if the trick ever worked in python3 but I remember often showing it to those who were new to python and the general awe I had over the nature of what was being expressed.

After playing around awhile I was convinced python didn't destroy functionality (it only changed the way it was operating). Here is a post talking about the "self referencing array" and it gives the multiline approach to creating it

```
&gt;&gt;&gt; my_list = [1,2]
&gt;&gt;&gt; my_list.append(my_list)
```

[ref](http://stackoverflow.com/questions/3728667/uses-of-self-referencing-lists)

I am sure someone smarter than me can tell you what changes in python such that the original format no longer works and likewise how to potentially express it again in one line (as the one line beauty of the self-referencing array was really what showed me the beauty in python). More so, even someone smarter then all us will have to tell you valid uses for this structure or what it looks like in memory and how you might use/need such a data structure.

TLDR: I am so old that python has nerfed the most beautiful quirk I know, the one-line self-referencing array.

Reply reply

[![u/Vitrivius avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_2.png)](https://www.reddit.com/user/Vitrivius/)

[Vitrivius](https://www.reddit.com/user/Vitrivius/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e4n01/)

```
a = [1,2,3,a]
```

That should raise a `NameError`, unless you already declared `a` somewhere else.

I find it hard to believe that this is something that actually worked in some old version of Python.

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e4n01/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dt9am/)

[](https://www.reddit.com/user/jroller/)

[jroller](https://www.reddit.com/user/jroller/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dqgs1/)

I enjoy the rare locals() abuse to create dicts.

```
def foo():
    """
    &gt;&gt;&gt; foo()
    {'a': 1, 'c': 3, 'b': 2}
    """
    a = 1
    b = 2
    c = 3
    return locals()
```

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dtt8e/)

My favorite quirk?

```
class Meta(type):
    def __getitem__(self, key):
        print("From class", key)

class Thing(metaclass=Meta):
    def __getitem__(self, key):
        print("From instance", key)

Thing[1] # From class 1
Thing()[1] # From instance 1
```

You can also do fun stuff like this in Python 3.

```
class Meta(type):
    def __new__(mcls, name, bases, attrs, **kwargs):
        # do stuff with the arbitrary keywords
    def __init__(cls, name, bases, attrs, **kwargs): # need to override this as well even if you don't use it

 class Thing(metaclass=Meta, key="word", other=4) # passed to **kwargs
```

Reply reply

[![u/DaemonXI avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/DaemonXI/)

[DaemonXI](https://www.reddit.com/user/DaemonXI/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e2l7u/)

I like foo\[:\] to clone an array.

Reply reply

[](https://www.reddit.com/user/thisaccountisbs/)

[thisaccountisbs](https://www.reddit.com/user/thisaccountisbs/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dgesn/)

Mutable defaults

def foo(bar=\[\]): bar.append('?') print bar

foo() foo()

Reply reply

[![u/ebrious avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/ebrious/)

[ebrious](https://www.reddit.com/user/ebrious/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dpys9/)

Are you aware of the ramifications of doing so? Every function call uses the same mutable object rather than instantiating a new one for each call [http://docs.quantifiedcode.com/python-anti-patterns/correctness/mutable\_default\_value\_as\_argument.html](http://docs.quantifiedcode.com/python-anti-patterns/correctness/mutable_default_value_as_argument.html). Its something that is strongly discouraged as a result.

Reply reply

1 more reply

1 more reply

[More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dpys9/) [More replies](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dgesn/)

[](https://www.reddit.com/user/Gr1pp717/)

[Gr1pp717](https://www.reddit.com/user/Gr1pp717/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4dwnl7/)

I don't think I would call this a "favorite" but I've had a few instances where a function would work fine ran in the console or as a script, but then fail in the main code.

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4e05u0/)

Nested list multiplication seems to make references instead of copies:

```
&gt;&gt;&gt; a = [[0, 0]]*2
&gt;&gt;&gt; a
[[0, 0], [0, 0]]
&gt;&gt;&gt; a[0][0] = 1
&gt;&gt;&gt; a
[[1, 0], [1, 0]]
```

Don't know whether to call it a quirk though, as making references makes some sense, but making copies would've been more convenient for what I was doing at the time.

Reply reply

[![u/ptmcg avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_3.png)](https://www.reddit.com/user/ptmcg/)

[ptmcg](https://www.reddit.com/user/ptmcg/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4eep0g/)

Using the equivalence of True and False to 1 and 0 to index into a tuple containing the true and false alternative values (old-style ternary):

```
def make_plural(name, n):
    return "%s%s" % (name, ('s','')[n == 1])

print ("I have %d %s." &amp; (qty, make_plural("apple", qty)))
```

But only do this if the alternatives are constants or local vars, or you will want the benefit of short-circuiting.

Reply reply

[![u/andreaskrueger avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_2.png)](https://www.reddit.com/user/andreaskrueger/)

[andreaskrueger](https://www.reddit.com/user/andreaskrueger/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4eqv5t/)

calling methods by their (string) names:

```
class foo(object): 
    def bar(self, x): print (x)

# only works if you know the method name at coding time:
foo().bar(23) 

# calling method by name string
fn_name = "bar"
fn = getattr(foo(), fn_name)
fn(42)
```

Reply reply

[![u/eacameron avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/eacameron/)

[eacameron](https://www.reddit.com/user/eacameron/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4kwati/)

In Python 3:

```
&gt;&gt;&gt; 00
0
&gt;&gt;&gt; 01
  File "&lt;stdin&gt;", line 1
    01
     ^
SyntaxError: invalid token
```

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4nbonu/)

My favourite is the rudimentary switch hack:

```
a = some_function_returning_a_string()
b = {
    'foo': foo_function,
    'bar': bar_function,
    'baz': baz_function,
    'default': default_function,
}
c = b.get(a, b['default'])()
```

Reply reply

\[deleted\]

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d78o2/)

more!!! :-)

Reply reply

[![u/pythoneeeer avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/pythoneeeer/)

[pythoneeeer](https://www.reddit.com/user/pythoneeeer/)

• [9y ago](https://www.reddit.com/r/Python/comments/4oje6w/comment/d4d9mkr/)
