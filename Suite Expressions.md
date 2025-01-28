---
Description: Suite Expressions - Alyssa Coghlan's Python Notes
Notes: python-ideas: http://mail.python.org/pipermail/python-ideas/2011-December/013003.html
author: 
Url: https://python-notes.curiousefficiency.org/en/latest/pep_ideas/suite_expr.html
Created: "2025-01-28  09:51:20"
Modified: 
Tags:
---

# Suite Expressions - Alyssa Coghlan's Python Notes

source: https://python-notes.curiousefficiency.org/en/latest/pep_ideas/suite_expr.html

> ## Excerpt
> python-ideas: http://mail.python.org/pipermail/python-ideas/2011-December/013003.html

---
# Suite Expressions[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/suite_expr.html#suite-expressions "Link to this heading")

python-ideas: [http://mail.python.org/pipermail/python-ideas/2011-December/013003.html](http://mail.python.org/pipermail/python-ideas/2011-December/013003.html)

This idea had an unusual start to life as a “devil’s advocate” style response to a long, rambling trollerific post to python-dev.

It ended up being a reasonably coherent write-up of a “delimited suites for Python” proposal that didn’t make me run screaming in horror, and several other people had similar reactions, so I decided to include a cleaned up version of it here.

If anyone does decide to take this idea and run with it, try running `from __future__ import braces` at the interactive prompt to get some idea of how big a can of worms you’re going to be opening (however, also remember that Guido’s views on the topic have [moderated somewhat](http://mail.python.org/pipermail/python-dev/2011-December/114871.html) over the years)

## Background[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/suite_expr.html#background "Link to this heading")

Python’s whitespace based delineation of suites is one of its greatest strengths. It aligns what the human reader perceives with what the computer is actually executing, reducing the frequency of semantic errors due to mismatches between the use of separate block delimiters and the human readable indentation.

However, this benefit comes at quite a high price: it is effectively impossible to embed arbitrary Python statements into any environment where leading whitespace is _not_ significant, including Python’s own expression syntax.

It can be argued that this restriction has led directly to the introduction of “expression friendly” variants of several Python top level constructs (for example, lambda expressions, conditional expressions and as a contributing factor in creating the various forms of comprehension).

It is also one of the reasons Python-based templating languages almost always create their own custom syntax - embedding Python’s own whitespace sensitive statement syntax into environments where leading whitespace is either ignored or forms a significant part of the template output is a formidable challenge.

In other languages, this kind of issue is handled by using explicit suite and statement delimiters (often braces and semi-colons, respectively) to allow full suites to be used as expressions.

## Rationale[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/suite_expr.html#rationale "Link to this heading")

To elaborate on the points made in the Background section, the reason significant leading whitespace can be problematic is due to two main circumstances:

1.  Attempting to transport it through a channel that either strips leading and trailing whitespace from lines, or else consolidates certain whitespace sequences into a single whitespace character (generally sequences of spaces and tabs becoming a single space). Python source code simply cannot be passed through such channels correctly - if they don’t offer an escaping mechanism, or that mechanism is not applied correctly, the code _will_ be corrupted. Explicitly delimited code, on the other hand, can be passed through without semantic alteration (even if the details of the whitespace change) and a pretty printer can fix it at the far end.
    
2.  Attempting to transport it through a channel where leading whitespace already has another meaning. This comes up primarily with templating languages - your whitespace is generally part of the template output, so it becomes problematic to break up your Python code across multiple code snippets while keeping the suite groupings clear. With explicit delimiters, though, you can just ignore the template parts, and pretend the code snippets are all part of a single string.
    

A delimited syntax allows definition of a standard way to pass Python source code through such channels. Since Python expression syntax is one such medium, this then leads immediately to the possibility of supporting multi-line lambdas (amongst other things).

## Proposal[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/suite_expr.html#proposal "Link to this heading")

While Python uses braces for another purpose (dictionary and set definitions), it is already the case that semi-colons (`;`) can be used as statement terminators, both optionally at the end of any simple statement, and also to combine multiple simple statements into a single larger statement (e.g. `x += y; print(x)`).

It seems that this existing feature could be combined with a brace-based notation to create an unambiguous “suite expression” syntax that would enjoy the same semantics as ordinary Python suites (i.e. doesn’t create a new scope, doesn’t directly affect control flow), but allows _all_ Python statements to be embedded inside expressions.

Currently, the character sequence `{:` is a Syntax Error: you are attempting to end a compound statement header line while an opening brace remains unmatched, or else trying to build a dictionary without specifying the key value. This creates an opportunity to re-use braces for a suite expression syntax without conflicting with their use for set and dictionary construction.

Specifically, it should be possible to create a variant of the top-level Python syntax that:

1.  Explicitly delimits suites using the notation `{:` to open the suite and `:}` to end it
    
2.  Requires the use of `;` to separate simple statements (i.e. newline characters would not end a statement, since we would be inside an expression)
    
3.  Allows compound statements to be used as simple statements by requiring that all subordinate suites also be suite expressions (i.e. leading whitespace would not be significant, since we would be using subexpressions to define each suite)
    

This would be sufficient to have a version of Python’s syntax that is both compatible with the existing syntax and could be embedded in whitespace-insensitive contexts without encountering problems with suite delineation. However, with one additional change, this new format could also be used to define “suite expressions” that could be used meaningfully anywhere Python currently accepts an expression:

4.  Uses the value of the last statement executed in the suite as the result of the overall suite expression (since return statements would affect the containing scope)
    

This would finally allow the oft-requested “multi-line lambdas”, since the body of the lambda could now be a suite expression.

## Examples[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/suite_expr.html#examples "Link to this heading")

Raise expressions:

```
<span></span><span class="n">x</span> <span class="o">=</span> <span class="n">y</span> <span class="k">if</span> <span class="n">y</span> <span class="ow">is</span> <span class="ow">not</span> <span class="kc">None</span> <span class="k">else</span> <span class="p">{:</span> <span class="k">raise</span> <span class="ne">ValueError</span><span class="p">(</span><span class="s2">"y must not be None!"</span><span class="p">)</span> <span class="p">:}</span>
```

Try expressions:

```
<span></span><span class="n">x</span> <span class="o">=</span> <span class="p">{:</span> <span class="k">try</span> <span class="p">{:</span> <span class="n">y</span><span class="o">.</span><span class="n">hello</span><span class="p">}</span> <span class="k">except</span> <span class="ne">AttributeError</span> <span class="p">{:</span> <span class="s2">"world!"</span><span class="p">}</span> <span class="p">:}</span>
```

With expressions:

```
<span></span><span class="n">data</span> <span class="o">=</span> <span class="p">{:</span> <span class="k">with</span> <span class="nb">open</span><span class="p">(</span><span class="n">fname</span><span class="p">)</span> <span class="k">as</span> <span class="n">f</span> <span class="p">{:</span> <span class="n">f</span><span class="o">.</span><span class="n">read</span><span class="p">()</span> <span class="p">:}</span> <span class="p">:}</span>
```

Embedded assignments:

```
<span></span><span class="k">if</span> <span class="p">{:</span> <span class="n">m</span> <span class="o">=</span> <span class="n">pat</span><span class="o">.</span><span class="n">search</span><span class="p">(</span><span class="n">data</span><span class="p">);</span> <span class="n">m</span> <span class="ow">is</span> <span class="ow">not</span> <span class="kc">None</span> <span class="p">:}:</span>
    <span class="c1"># do something with m</span>
<span class="k">else</span><span class="p">:</span>
    <span class="c1"># No match!</span>
```

In-order conditional expressions:

```
<span></span><span class="n">x</span> <span class="o">=</span> <span class="p">{:</span> <span class="k">if</span> <span class="n">a</span> <span class="p">{:</span><span class="n">b</span><span class="p">:}</span> <span class="k">else</span> <span class="p">{:</span><span class="n">c</span><span class="p">:}</span> <span class="p">:}</span>
```

One-line accumulator function:

```
<span></span><span class="k">def</span> <span class="nf">acc</span><span class="p">(</span><span class="n">n</span><span class="o">=</span><span class="mi">0</span><span class="p">):</span> <span class="k">return</span> <span class="k">lambda</span> <span class="p">(</span><span class="n">i</span><span class="p">)</span> <span class="p">{:</span> <span class="k">nonlocal</span> <span class="n">n</span><span class="p">;</span> <span class="n">n</span> <span class="o">+=</span> <span class="n">i</span><span class="p">;</span> <span class="n">n</span> <span class="p">:}</span>
```

A Python-based templating engine (\[[1](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/suite_expr.html#id1)\]):

```
<span></span>&lt;% if danger_level &gt; 3 {: %&gt;

&lt;div class="alert"&gt;
  &lt;% if danger_level == 5 {: %&gt;EXTREME &lt;% :} %&gt;DANGER ALERT!
&lt;/div&gt;

&lt;% :} elif danger_level &gt; 0 {: %&gt;

&lt;div&gt;Some chance of danger&lt;/div&gt;

&lt;% :} else {: %&gt;

&lt;div&gt;No danger&lt;/div&gt;

&lt;% :} %&gt;

&lt;% for a in ['cat', 'dog', 'rabbit'] {: %&gt;

&lt;h2&gt;&lt;%= a %&gt;&lt;/h2&gt;
&lt;p&gt;&lt;%= describe_animal(a) %&gt;&lt;/p&gt;

&lt;% :} %&gt;
```

\[1\]

Based on an initial example by Simon Baird: [https://gist.github.com/1455210](https://gist.github.com/1455210)
