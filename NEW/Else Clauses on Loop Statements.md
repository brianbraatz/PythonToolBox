---
Description: Else Clauses on Loop Statements - Alyssa Coghlan's Python Notes
Notes: Python’s loop statements have a feature that some people love (Hi!), some
people hate, many have never encountered and many just find confusing: an
else clause.
author: 
Url: https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html
Created: "2025-01-28  09:48:12"
Modified: 
Tags:
---

# Else Clauses on Loop Statements - Alyssa Coghlan's Python Notes

source: https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html

> ## Excerpt
> Python’s loop statements have a feature that some people love (Hi!), some
people hate, many have never encountered and many just find confusing: an
else clause.

---
# Else Clauses on Loop Statements[¶](https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html#else-clauses-on-loop-statements "Link to this heading")

Python’s loop statements have a feature that some people love (Hi!), some people hate, many have never encountered and many just find confusing: an `else` clause.

This article endeavours to explain some of the reasons behind the frequent confusion, and explore some other ways of thinking about the problem that give a better idea of what is _really_ going on with these clauses.

## Reasons for Confusion[¶](https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html#reasons-for-confusion "Link to this heading")

The major reason many developers find the behaviour of these clauses potentially confusing is shown in the following example:

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="k">if</span> <span class="p">[</span><span class="mi">1</span><span class="p">]:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Then"</span><span class="p">)</span>
<span class="gp">... </span><span class="k">else</span><span class="p">:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Else"</span><span class="p">)</span>
<span class="gp">...</span>
<span class="go">Then</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="p">[</span><span class="mi">1</span><span class="p">]:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Then"</span><span class="p">)</span>
<span class="gp">... </span><span class="k">else</span><span class="p">:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Else"</span><span class="p">)</span>
<span class="gp">...</span>
<span class="go">Then</span>
<span class="go">Else</span>
```

The `if <iterable>` header looks very similar to the `for <var> in <iterable>` header, so it’s quite natural for people to assume they’re related and expect the `else` clause to be skipped in both cases. As the example shows, this assumption is incorrect: in the second case, the else clauses triggers even though the iterable isn’t empty.

If we then look at a common `while` loop pattern instead, it just deepens the confusion because _it_ seems to line up with the way we would expect the conditional to work:

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">x</span> <span class="o">=</span> <span class="p">[</span><span class="mi">1</span><span class="p">]</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">while</span> <span class="n">x</span><span class="p">:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Then"</span><span class="p">)</span>
<span class="gp">... </span>    <span class="n">x</span><span class="o">.</span><span class="n">pop</span><span class="p">()</span>
<span class="gp">... </span><span class="k">else</span><span class="p">:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Else"</span><span class="p">)</span>
<span class="gp">...</span>
<span class="go">Then</span>
<span class="go">Else</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">if</span> <span class="n">x</span><span class="p">:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Then"</span><span class="p">)</span>
<span class="gp">... </span><span class="k">else</span><span class="p">:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Else"</span><span class="p">)</span>
<span class="gp">...</span>
<span class="go">Else</span>
```

Here, the loop runs until the iterable is empty, and then the `else` clause is executed, just as it is in the `if` statement.

## A different kind of `else`[¶](https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html#a-different-kind-of-else "Link to this heading")

So what’s going on? The truth is that the superficial similarity between `if <iterable>` and `for <var> in <iterable>` is rather deceptive. If we call the `else` clause on an `if` statement a “conditional else”, then we can look to `try` statements for a different _kind_ of `else` clause, a “completion clause”:

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="k">try</span><span class="p">:</span>
<span class="gp">... </span>    <span class="k">pass</span>
<span class="gp">... </span><span class="k">except</span><span class="p">:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Then"</span><span class="p">)</span> <span class="c1"># The try block threw an exception</span>
<span class="gp">... </span><span class="k">else</span><span class="p">:</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="s2">"Else"</span><span class="p">)</span> <span class="c1"># The try block didn't throw an exception</span>
<span class="gp">...</span>
<span class="go">Else</span>
```

With a completion clause, the question being asked has to do with how an earlier suite of code _finished_, rather than checking the boolean value of an expression. Reaching the `else` clause in a `try` statement means that the try block actually completed successfully - it didn’t throw an exception or otherwise terminate before reaching the end of the suite.

This is actually a much better model for what’s going on in our `for` loop, since the condition the `else` is checking for is whether or not the loop was explicitly terminated by a `break` statement. While it’s not legal syntax, it may be helpful to mentally insert an `except break: pass` whenever you encounter a loop with an associated `else` clause in order to help remember what it means:

```
<span></span><span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">iterable</span><span class="p">:</span>
    <span class="o">...</span>
<span class="k">except</span> <span class="k">break</span><span class="p">:</span>
    <span class="k">pass</span> <span class="c1"># Implied by Python's loop semantics</span>
<span class="k">else</span><span class="p">:</span>
    <span class="o">...</span>  <span class="c1"># No break statement was encountered</span>

<span class="k">while</span> <span class="n">condition</span><span class="p">:</span>
    <span class="o">...</span>
<span class="k">except</span> <span class="k">break</span><span class="p">:</span>
    <span class="k">pass</span> <span class="c1"># Implied by Python's loop semantics</span>
<span class="k">else</span><span class="p">:</span>
    <span class="o">...</span>  <span class="c1"># No break statement was encountered</span>
```

## What possible use is the current behaviour?[¶](https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html#what-possible-use-is-the-current-behaviour "Link to this heading")

The main use case for this behaviour is to implement search loops, where you’re performing a search for an item that meets a particular condition, and need to perform additional processing or raise an informative error if no acceptable value is found:

```
<span></span><span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">data</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">acceptable</span><span class="p">(</span><span class="n">x</span><span class="p">):</span>
        <span class="k">break</span>
<span class="k">else</span><span class="p">:</span>
    <span class="k">raise</span> <span class="ne">ValueError</span><span class="p">(</span><span class="s2">"No acceptable value in </span><span class="si">{!r:100}</span><span class="s2">"</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">data</span><span class="p">))</span>

<span class="o">...</span> <span class="c1"># Continue calculations with x</span>
```

## But how do I check if my loop never ran at all?[¶](https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html#but-how-do-i-check-if-my-loop-never-ran-at-all "Link to this heading")

The easiest way to check if a `for` loop never executed is to use `None` as a sentinel value:

```
<span></span><span class="n">x</span> <span class="o">=</span> <span class="kc">None</span>
<span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">data</span><span class="p">:</span>
    <span class="o">...</span> <span class="c1"># process x</span>
<span class="k">if</span> <span class="n">x</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
    <span class="k">raise</span> <span class="ne">ValueError</span><span class="p">(</span><span class="s2">"Empty data iterable: </span><span class="si">{!r:100}</span><span class="s2">"</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">data</span><span class="p">))</span>
```

If `None` is a legitimate data value, then a custom sentinel object can be used instead:

```
<span></span><span class="n">x</span> <span class="o">=</span> <span class="n">_empty</span> <span class="o">=</span> <span class="nb">object</span><span class="p">()</span>
<span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">data</span><span class="p">:</span>
    <span class="o">...</span> <span class="c1"># process x</span>
<span class="k">if</span> <span class="n">x</span> <span class="ow">is</span> <span class="n">_empty</span><span class="p">:</span>
    <span class="k">raise</span> <span class="ne">ValueError</span><span class="p">(</span><span class="s2">"Empty data iterable: </span><span class="si">{!r:100}</span><span class="s2">"</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">data</span><span class="p">))</span>
```

For `while` loops, the appropriate solution will depend on the details of the loop.

## But couldn’t Python be different?[¶](https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html#but-couldn-t-python-be-different "Link to this heading")

Backwards compatibility constraints and the general desire not to change the language core without a compelling justification mean that the answer to this question is likely always going to be “No”.

The simplest approach for any new language to take to avoid the confusion encountered in relation to this feature of Python would be to just leave it out altogether. Many (most?) other languages don’t offer it, and there are certainly other ways to handle the search loop use case, including a sentinel based approach similar to that used to detect whether or not a loop ran at all:

```
<span></span><span class="n">result</span> <span class="o">=</span> <span class="n">_not_found</span> <span class="o">=</span> <span class="nb">object</span><span class="p">()</span>
<span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">data</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">acceptable</span><span class="p">(</span><span class="n">x</span><span class="p">):</span>
        <span class="n">result</span> <span class="o">=</span> <span class="n">x</span>
        <span class="k">break</span>
<span class="k">if</span> <span class="n">result</span> <span class="ow">is</span> <span class="n">_not_found</span><span class="p">:</span>
    <span class="k">raise</span> <span class="ne">ValueError</span><span class="p">(</span><span class="s2">"No acceptable value in </span><span class="si">{!r:100}</span><span class="s2">"</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">data</span><span class="p">))</span>

<span class="o">...</span> <span class="c1"># Continue calculations with result</span>
```

## Closing note: Not so different after all?[¶](https://python-notes.curiousefficiency.org/en/latest/python_concepts/break_else.html#closing-note-not-so-different-after-all "Link to this heading")

Attentive readers may have noticed that the behaviour of `while` loops still makes sense regardless of whether you think of their `else` clause as a conditional else or as a completion clause. We can think of a `while` statement in terms of an infinite loop containing a `break` statement:

```
<span></span><span class="k">while</span> <span class="kc">True</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">condition</span><span class="p">:</span>
        <span class="k">pass</span> <span class="c1"># Implied by Python's loop semantics</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="o">...</span> <span class="c1"># While loop else clause runs here</span>
        <span class="k">break</span>
    <span class="o">...</span> <span class="c1"># While loop body runs here</span>
```

If you dig deep enough, it’s also possible to relate the completion clause constructs in `try` statements and `for` loops back to the basic conditional else construct. The thing to remember though, is that it is only `while` loops and `if` statements that are checking the boolean value of an expression, while `for` loops and `try` statements are checking whether or not a section of code was aborted before completing normally.

However, digging to that deeper level doesn’t really provide much more enlightenment when it comes to understanding how the two different forms of `else` clause work in practice.
