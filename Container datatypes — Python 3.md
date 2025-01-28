---
Description: collections — Container datatypes — Python 3.13.1 documentation
Notes: Source code: Lib/collections/__init__.py This module implements specialized container datatypes providing alternatives to Python’s general purpose built-in containers, dict, list, set, and tuple.,,...
author: 
Url: https://docs.python.org/3/library/collections.html
Created: "2025-01-28  09:45:45"
Modified: 
Tags:
---

# collections — Container datatypes — Python 3.13.1 documentation

source: https://docs.python.org/3/library/collections.html

> ## Excerpt
> Source code: Lib/collections/__init__.py This module implements specialized container datatypes providing alternatives to Python’s general purpose built-in containers, dict, list, set, and tuple.,,...

---
# `collections` — Container datatypes[¶](https://docs.python.org/3/library/collections.html#module-collections "Link to this heading")

**Source code:** [Lib/collections/\_\_init\_\_.py](https://github.com/python/cpython/tree/3.13/Lib/collections/__init__.py)

___

This module implements specialized container datatypes providing alternatives to Python’s general purpose built-in containers, [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict"), [`list`](https://docs.python.org/3/library/collections.htmlstdtypes.html#list "list"), [`set`](https://docs.python.org/3/library/collections.htmlstdtypes.html#set "set"), and [`tuple`](https://docs.python.org/3/library/collections.htmlstdtypes.html#tuple "tuple").

<table class="docutils align-default"><tbody><tr class="row-odd"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.namedtuple" title="collections.namedtuple"><code class="xref py py-func docutils literal notranslate"><span class="pre">namedtuple()</span></code></a></p></td><td><p>factory function for creating tuple subclasses with named fields</p></td></tr><tr class="row-even"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.deque" title="collections.deque"><code class="xref py py-class docutils literal notranslate"><span class="pre">deque</span></code></a></p></td><td><p>list-like container with fast appends and pops on either end</p></td></tr><tr class="row-odd"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.ChainMap" title="collections.ChainMap"><code class="xref py py-class docutils literal notranslate"><span class="pre">ChainMap</span></code></a></p></td><td><p>dict-like class for creating a single view of multiple mappings</p></td></tr><tr class="row-even"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.Counter" title="collections.Counter"><code class="xref py py-class docutils literal notranslate"><span class="pre">Counter</span></code></a></p></td><td><p>dict subclass for counting <a class="reference internal" href="https://docs.python.org/3/library/collections.html../glossary.html#term-hashable"><span class="xref std std-term">hashable</span></a> objects</p></td></tr><tr class="row-odd"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.OrderedDict" title="collections.OrderedDict"><code class="xref py py-class docutils literal notranslate"><span class="pre">OrderedDict</span></code></a></p></td><td><p>dict subclass that remembers the order entries were added</p></td></tr><tr class="row-even"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.defaultdict" title="collections.defaultdict"><code class="xref py py-class docutils literal notranslate"><span class="pre">defaultdict</span></code></a></p></td><td><p>dict subclass that calls a factory function to supply missing values</p></td></tr><tr class="row-odd"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.UserDict" title="collections.UserDict"><code class="xref py py-class docutils literal notranslate"><span class="pre">UserDict</span></code></a></p></td><td><p>wrapper around dictionary objects for easier dict subclassing</p></td></tr><tr class="row-even"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.UserList" title="collections.UserList"><code class="xref py py-class docutils literal notranslate"><span class="pre">UserList</span></code></a></p></td><td><p>wrapper around list objects for easier list subclassing</p></td></tr><tr class="row-odd"><td><p><a class="reference internal" href="https://docs.python.org/3/library/collections.html#collections.UserString" title="collections.UserString"><code class="xref py py-class docutils literal notranslate"><span class="pre">UserString</span></code></a></p></td><td><p>wrapper around string objects for easier string subclassing</p></td></tr></tbody></table>

## [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") objects[¶](https://docs.python.org/3/library/collections.html#chainmap-objects "Link to this heading")

Added in version 3.3.

A [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") class is provided for quickly linking a number of mappings so they can be treated as a single unit. It is often much faster than creating a new dictionary and running multiple [`update()`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict.update "dict.update") calls.

The class can be used to simulate nested scopes and is useful in templating.

_class_ collections.ChainMap(_\*maps_)[¶](https://docs.python.org/3/library/collections.html#collections.ChainMap "Link to this definition")

A [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") groups multiple dicts or other mappings together to create a single, updateable view. If no _maps_ are specified, a single empty dictionary is provided so that a new chain always has at least one mapping.

The underlying mappings are stored in a list. That list is public and can be accessed or updated using the _maps_ attribute. There is no other state.

Lookups search the underlying mappings successively until a key is found. In contrast, writes, updates, and deletions only operate on the first mapping.

A [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") incorporates the underlying mappings by reference. So, if one of the underlying mappings gets updated, those changes will be reflected in [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap").

All of the usual dictionary methods are supported. In addition, there is a _maps_ attribute, a method for creating new subcontexts, and a property for accessing all but the first mapping:

maps[¶](https://docs.python.org/3/library/collections.html#collections.ChainMap.maps "Link to this definition")

A user updateable list of mappings. The list is ordered from first-searched to last-searched. It is the only stored state and can be modified to change which mappings are searched. The list should always contain at least one mapping.

new\_child(_m\=None_, _\*\*kwargs_)[¶](https://docs.python.org/3/library/collections.html#collections.ChainMap.new_child "Link to this definition")

Returns a new [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") containing a new map followed by all of the maps in the current instance. If `m` is specified, it becomes the new map at the front of the list of mappings; if not specified, an empty dict is used, so that a call to `d.new_child()` is equivalent to: `ChainMap({}, *d.maps)`. If any keyword arguments are specified, they update passed map or new empty dict. This method is used for creating subcontexts that can be updated without altering values in any of the parent mappings.

Changed in version 3.4: The optional `m` parameter was added.

Changed in version 3.10: Keyword arguments support was added.

parents[¶](https://docs.python.org/3/library/collections.html#collections.ChainMap.parents "Link to this definition")

Property returning a new [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") containing all of the maps in the current instance except the first one. This is useful for skipping the first map in the search. Use cases are similar to those for the [`nonlocal`](https://docs.python.org/3/library/collections.html../reference/simple_stmts.html#nonlocal) keyword used in [nested scopes](https://docs.python.org/3/library/collections.html../glossary.html#term-nested-scope). The use cases also parallel those for the built-in [`super()`](https://docs.python.org/3/library/collections.htmlfunctions.html#super "super") function. A reference to `d.parents` is equivalent to: `ChainMap(*d.maps[1:])`.

Note, the iteration order of a [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") is determined by scanning the mappings last to first:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">baseline</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'music'</span><span class="p">:</span> <span class="s1">'bach'</span><span class="p">,</span> <span class="s1">'art'</span><span class="p">:</span> <span class="s1">'rembrandt'</span><span class="p">}</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">adjustments</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'art'</span><span class="p">:</span> <span class="s1">'van gogh'</span><span class="p">,</span> <span class="s1">'opera'</span><span class="p">:</span> <span class="s1">'carmen'</span><span class="p">}</span>
<span class="gp">&gt;&gt;&gt; </span><span class="nb">list</span><span class="p">(</span><span class="n">ChainMap</span><span class="p">(</span><span class="n">adjustments</span><span class="p">,</span> <span class="n">baseline</span><span class="p">))</span>
<span class="go">['music', 'art', 'opera']</span>
```

This gives the same ordering as a series of [`dict.update()`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict.update "dict.update") calls starting with the last mapping:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">combined</span> <span class="o">=</span> <span class="n">baseline</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">combined</span><span class="o">.</span><span class="n">update</span><span class="p">(</span><span class="n">adjustments</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="nb">list</span><span class="p">(</span><span class="n">combined</span><span class="p">)</span>
<span class="go">['music', 'art', 'opera']</span>
```

Changed in version 3.9: Added support for `|` and `|=` operators, specified in [**PEP 584**](https://peps.python.org/pep-0584/).

See also

-   The [MultiContext class](https://github.com/enthought/codetools/blob/4.0.0/codetools/contexts/multi_context.py) in the Enthought [CodeTools package](https://github.com/enthought/codetools) has options to support writing to any mapping in the chain.
    
-   Django’s [Context class](https://github.com/django/django/blob/main/django/template/context.py) for templating is a read-only chain of mappings. It also features pushing and popping of contexts similar to the [`new_child()`](https://docs.python.org/3/library/collections.html#collections.ChainMap.new_child "collections.ChainMap.new_child") method and the [`parents`](https://docs.python.org/3/library/collections.html#collections.ChainMap.parents "collections.ChainMap.parents") property.
    
-   The [Nested Contexts recipe](https://code.activestate.com/recipes/577434-nested-contexts-a-chain-of-mapping-objects/) has options to control whether writes and other mutations apply only to the first mapping or to any mapping in the chain.
    
-   A [greatly simplified read-only version of Chainmap](https://code.activestate.com/recipes/305268/).
    

### [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") Examples and Recipes[¶](https://docs.python.org/3/library/collections.html#chainmap-examples-and-recipes "Link to this heading")

This section shows various approaches to working with chained maps.

Example of simulating Python’s internal lookup chain:

```
<span></span><span class="kn">import</span><span class="w"> </span><span class="nn">builtins</span>
<span class="n">pylookup</span> <span class="o">=</span> <span class="n">ChainMap</span><span class="p">(</span><span class="nb">locals</span><span class="p">(),</span> <span class="nb">globals</span><span class="p">(),</span> <span class="nb">vars</span><span class="p">(</span><span class="n">builtins</span><span class="p">))</span>
```

Example of letting user specified command-line arguments take precedence over environment variables which in turn take precedence over default values:

```
<span></span><span class="kn">import</span><span class="w"> </span><span class="nn">os</span><span class="o">,</span><span class="w"> </span><span class="nn">argparse</span>

<span class="n">defaults</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'color'</span><span class="p">:</span> <span class="s1">'red'</span><span class="p">,</span> <span class="s1">'user'</span><span class="p">:</span> <span class="s1">'guest'</span><span class="p">}</span>

<span class="n">parser</span> <span class="o">=</span> <span class="n">argparse</span><span class="o">.</span><span class="n">ArgumentParser</span><span class="p">()</span>
<span class="n">parser</span><span class="o">.</span><span class="n">add_argument</span><span class="p">(</span><span class="s1">'-u'</span><span class="p">,</span> <span class="s1">'--user'</span><span class="p">)</span>
<span class="n">parser</span><span class="o">.</span><span class="n">add_argument</span><span class="p">(</span><span class="s1">'-c'</span><span class="p">,</span> <span class="s1">'--color'</span><span class="p">)</span>
<span class="n">namespace</span> <span class="o">=</span> <span class="n">parser</span><span class="o">.</span><span class="n">parse_args</span><span class="p">()</span>
<span class="n">command_line_args</span> <span class="o">=</span> <span class="p">{</span><span class="n">k</span><span class="p">:</span> <span class="n">v</span> <span class="k">for</span> <span class="n">k</span><span class="p">,</span> <span class="n">v</span> <span class="ow">in</span> <span class="nb">vars</span><span class="p">(</span><span class="n">namespace</span><span class="p">)</span><span class="o">.</span><span class="n">items</span><span class="p">()</span> <span class="k">if</span> <span class="n">v</span> <span class="ow">is</span> <span class="ow">not</span> <span class="kc">None</span><span class="p">}</span>

<span class="n">combined</span> <span class="o">=</span> <span class="n">ChainMap</span><span class="p">(</span><span class="n">command_line_args</span><span class="p">,</span> <span class="n">os</span><span class="o">.</span><span class="n">environ</span><span class="p">,</span> <span class="n">defaults</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">combined</span><span class="p">[</span><span class="s1">'color'</span><span class="p">])</span>
<span class="nb">print</span><span class="p">(</span><span class="n">combined</span><span class="p">[</span><span class="s1">'user'</span><span class="p">])</span>
```

Example patterns for using the [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") class to simulate nested contexts:

```
<span></span><span class="n">c</span> <span class="o">=</span> <span class="n">ChainMap</span><span class="p">()</span>        <span class="c1"># Create root context</span>
<span class="n">d</span> <span class="o">=</span> <span class="n">c</span><span class="o">.</span><span class="n">new_child</span><span class="p">()</span>     <span class="c1"># Create nested child context</span>
<span class="n">e</span> <span class="o">=</span> <span class="n">c</span><span class="o">.</span><span class="n">new_child</span><span class="p">()</span>     <span class="c1"># Child of c, independent from d</span>
<span class="n">e</span><span class="o">.</span><span class="n">maps</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>             <span class="c1"># Current context dictionary -- like Python's locals()</span>
<span class="n">e</span><span class="o">.</span><span class="n">maps</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>            <span class="c1"># Root context -- like Python's globals()</span>
<span class="n">e</span><span class="o">.</span><span class="n">parents</span>             <span class="c1"># Enclosing context chain -- like Python's nonlocals</span>

<span class="n">d</span><span class="p">[</span><span class="s1">'x'</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>            <span class="c1"># Set value in current context</span>
<span class="n">d</span><span class="p">[</span><span class="s1">'x'</span><span class="p">]</span>                <span class="c1"># Get first key in the chain of contexts</span>
<span class="k">del</span> <span class="n">d</span><span class="p">[</span><span class="s1">'x'</span><span class="p">]</span>            <span class="c1"># Delete from current context</span>
<span class="nb">list</span><span class="p">(</span><span class="n">d</span><span class="p">)</span>               <span class="c1"># All nested values</span>
<span class="n">k</span> <span class="ow">in</span> <span class="n">d</span>                <span class="c1"># Check all nested values</span>
<span class="nb">len</span><span class="p">(</span><span class="n">d</span><span class="p">)</span>                <span class="c1"># Number of nested values</span>
<span class="n">d</span><span class="o">.</span><span class="n">items</span><span class="p">()</span>             <span class="c1"># All nested items</span>
<span class="nb">dict</span><span class="p">(</span><span class="n">d</span><span class="p">)</span>               <span class="c1"># Flatten into a regular dictionary</span>
```

The [`ChainMap`](https://docs.python.org/3/library/collections.html#collections.ChainMap "collections.ChainMap") class only makes updates (writes and deletions) to the first mapping in the chain while lookups will search the full chain. However, if deep writes and deletions are desired, it is easy to make a subclass that updates keys found deeper in the chain:

```
<span></span><span class="k">class</span><span class="w"> </span><span class="nc">DeepChainMap</span><span class="p">(</span><span class="n">ChainMap</span><span class="p">):</span>
    <span class="s1">'Variant of ChainMap that allows direct updates to inner scopes'</span>

    <span class="k">def</span><span class="w"> </span><span class="fm">__setitem__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">key</span><span class="p">,</span> <span class="n">value</span><span class="p">):</span>
        <span class="k">for</span> <span class="n">mapping</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">maps</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">key</span> <span class="ow">in</span> <span class="n">mapping</span><span class="p">:</span>
                <span class="n">mapping</span><span class="p">[</span><span class="n">key</span><span class="p">]</span> <span class="o">=</span> <span class="n">value</span>
                <span class="k">return</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">maps</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="n">key</span><span class="p">]</span> <span class="o">=</span> <span class="n">value</span>

    <span class="k">def</span><span class="w"> </span><span class="fm">__delitem__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">key</span><span class="p">):</span>
        <span class="k">for</span> <span class="n">mapping</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">maps</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">key</span> <span class="ow">in</span> <span class="n">mapping</span><span class="p">:</span>
                <span class="k">del</span> <span class="n">mapping</span><span class="p">[</span><span class="n">key</span><span class="p">]</span>
                <span class="k">return</span>
        <span class="k">raise</span> <span class="ne">KeyError</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>

<span class="o">&gt;&gt;&gt;</span> <span class="n">d</span> <span class="o">=</span> <span class="n">DeepChainMap</span><span class="p">({</span><span class="s1">'zebra'</span><span class="p">:</span> <span class="s1">'black'</span><span class="p">},</span> <span class="p">{</span><span class="s1">'elephant'</span><span class="p">:</span> <span class="s1">'blue'</span><span class="p">},</span> <span class="p">{</span><span class="s1">'lion'</span><span class="p">:</span> <span class="s1">'yellow'</span><span class="p">})</span>
<span class="o">&gt;&gt;&gt;</span> <span class="n">d</span><span class="p">[</span><span class="s1">'lion'</span><span class="p">]</span> <span class="o">=</span> <span class="s1">'orange'</span>         <span class="c1"># update an existing key two levels down</span>
<span class="o">&gt;&gt;&gt;</span> <span class="n">d</span><span class="p">[</span><span class="s1">'snake'</span><span class="p">]</span> <span class="o">=</span> <span class="s1">'red'</span>           <span class="c1"># new keys get added to the topmost dict</span>
<span class="o">&gt;&gt;&gt;</span> <span class="k">del</span> <span class="n">d</span><span class="p">[</span><span class="s1">'elephant'</span><span class="p">]</span>            <span class="c1"># remove an existing key one level down</span>
<span class="o">&gt;&gt;&gt;</span> <span class="n">d</span>                            <span class="c1"># display result</span>
<span class="n">DeepChainMap</span><span class="p">({</span><span class="s1">'zebra'</span><span class="p">:</span> <span class="s1">'black'</span><span class="p">,</span> <span class="s1">'snake'</span><span class="p">:</span> <span class="s1">'red'</span><span class="p">},</span> <span class="p">{},</span> <span class="p">{</span><span class="s1">'lion'</span><span class="p">:</span> <span class="s1">'orange'</span><span class="p">})</span>
```

## [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") objects[¶](https://docs.python.org/3/library/collections.html#counter-objects "Link to this heading")

A counter tool is provided to support convenient and rapid tallies. For example:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="c1"># Tally occurrences of words in a list</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">cnt</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">()</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">word</span> <span class="ow">in</span> <span class="p">[</span><span class="s1">'red'</span><span class="p">,</span> <span class="s1">'blue'</span><span class="p">,</span> <span class="s1">'red'</span><span class="p">,</span> <span class="s1">'green'</span><span class="p">,</span> <span class="s1">'blue'</span><span class="p">,</span> <span class="s1">'blue'</span><span class="p">]:</span>
<span class="gp">... </span>    <span class="n">cnt</span><span class="p">[</span><span class="n">word</span><span class="p">]</span> <span class="o">+=</span> <span class="mi">1</span>
<span class="gp">...</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">cnt</span>
<span class="go">Counter({'blue': 3, 'red': 2, 'green': 1})</span>

<span class="gp">&gt;&gt;&gt; </span><span class="c1"># Find the ten most common words in Hamlet</span>
<span class="gp">&gt;&gt;&gt; </span><span class="kn">import</span><span class="w"> </span><span class="nn">re</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">words</span> <span class="o">=</span> <span class="n">re</span><span class="o">.</span><span class="n">findall</span><span class="p">(</span><span class="sa">r</span><span class="s1">'\w+'</span><span class="p">,</span> <span class="nb">open</span><span class="p">(</span><span class="s1">'hamlet.txt'</span><span class="p">)</span><span class="o">.</span><span class="n">read</span><span class="p">()</span><span class="o">.</span><span class="n">lower</span><span class="p">())</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Counter</span><span class="p">(</span><span class="n">words</span><span class="p">)</span><span class="o">.</span><span class="n">most_common</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
<span class="go">[('the', 1143), ('and', 966), ('to', 762), ('of', 669), ('i', 631),</span>
<span class="go"> ('you', 554),  ('a', 546), ('my', 514), ('hamlet', 471), ('in', 451)]</span>
```

_class_ collections.Counter(\[_iterable-or-mapping_\])[¶](https://docs.python.org/3/library/collections.html#collections.Counter "Link to this definition")

A [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") is a [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") subclass for counting [hashable](https://docs.python.org/3/library/collections.html../glossary.html#term-hashable) objects. It is a collection where elements are stored as dictionary keys and their counts are stored as dictionary values. Counts are allowed to be any integer value including zero or negative counts. The [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") class is similar to bags or multisets in other languages.

Elements are counted from an _iterable_ or initialized from another _mapping_ (or counter):

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">()</span>                           <span class="c1"># a new, empty counter</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="s1">'gallahad'</span><span class="p">)</span>                 <span class="c1"># a new counter from an iterable</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">({</span><span class="s1">'red'</span><span class="p">:</span> <span class="mi">4</span><span class="p">,</span> <span class="s1">'blue'</span><span class="p">:</span> <span class="mi">2</span><span class="p">})</span>      <span class="c1"># a new counter from a mapping</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">cats</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span> <span class="n">dogs</span><span class="o">=</span><span class="mi">8</span><span class="p">)</span>             <span class="c1"># a new counter from keyword args</span>
```

Counter objects have a dictionary interface except that they return a zero count for missing items instead of raising a [`KeyError`](https://docs.python.org/3/library/collections.htmlexceptions.html#KeyError "KeyError"):

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">([</span><span class="s1">'eggs'</span><span class="p">,</span> <span class="s1">'ham'</span><span class="p">])</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span><span class="p">[</span><span class="s1">'bacon'</span><span class="p">]</span>                              <span class="c1"># count of a missing element is zero</span>
<span class="go">0</span>
```

Setting a count to zero does not remove an element from a counter. Use `del` to remove it entirely:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">c</span><span class="p">[</span><span class="s1">'sausage'</span><span class="p">]</span> <span class="o">=</span> <span class="mi">0</span>                        <span class="c1"># counter entry with a zero count</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">del</span> <span class="n">c</span><span class="p">[</span><span class="s1">'sausage'</span><span class="p">]</span>                        <span class="c1"># del actually removes the entry</span>
```

Added in version 3.1.

Changed in version 3.7: As a [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") subclass, [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") inherited the capability to remember insertion order. Math operations on _Counter_ objects also preserve order. Results are ordered according to when an element is first encountered in the left operand and then by the order encountered in the right operand.

Counter objects support additional methods beyond those available for all dictionaries:

elements()[¶](https://docs.python.org/3/library/collections.html#collections.Counter.elements "Link to this definition")

Return an iterator over elements repeating each as many times as its count. Elements are returned in the order first encountered. If an element’s count is less than one, [`elements()`](https://docs.python.org/3/library/collections.html#collections.Counter.elements "collections.Counter.elements") will ignore it.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">a</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span> <span class="n">c</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">d</span><span class="o">=-</span><span class="mi">2</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="nb">sorted</span><span class="p">(</span><span class="n">c</span><span class="o">.</span><span class="n">elements</span><span class="p">())</span>
<span class="go">['a', 'a', 'a', 'a', 'b', 'b']</span>
```

most\_common(\[_n_\])[¶](https://docs.python.org/3/library/collections.html#collections.Counter.most_common "Link to this definition")

Return a list of the _n_ most common elements and their counts from the most common to the least. If _n_ is omitted or `None`, [`most_common()`](https://docs.python.org/3/library/collections.html#collections.Counter.most_common "collections.Counter.most_common") returns _all_ elements in the counter. Elements with equal counts are ordered in the order first encountered:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">Counter</span><span class="p">(</span><span class="s1">'abracadabra'</span><span class="p">)</span><span class="o">.</span><span class="n">most_common</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
<span class="go">[('a', 5), ('b', 2), ('r', 2)]</span>
```

subtract(\[_iterable-or-mapping_\])[¶](https://docs.python.org/3/library/collections.html#collections.Counter.subtract "Link to this definition")

Elements are subtracted from an _iterable_ or from another _mapping_ (or counter). Like [`dict.update()`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict.update "dict.update") but subtracts counts instead of replacing them. Both inputs and outputs may be zero or negative.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">a</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span> <span class="n">c</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">d</span><span class="o">=-</span><span class="mi">2</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">a</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span> <span class="n">c</span><span class="o">=</span><span class="mi">3</span><span class="p">,</span> <span class="n">d</span><span class="o">=</span><span class="mi">4</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span><span class="o">.</span><span class="n">subtract</span><span class="p">(</span><span class="n">d</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span>
<span class="go">Counter({'a': 3, 'b': 0, 'c': -3, 'd': -6})</span>
```

Added in version 3.2.

total()[¶](https://docs.python.org/3/library/collections.html#collections.Counter.total "Link to this definition")

Compute the sum of the counts.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">a</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">c</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span><span class="o">.</span><span class="n">total</span><span class="p">()</span>
<span class="go">15</span>
```

Added in version 3.10.

The usual dictionary methods are available for [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") objects except for two which work differently for counters.

fromkeys(_iterable_)[¶](https://docs.python.org/3/library/collections.html#collections.Counter.fromkeys "Link to this definition")

This class method is not implemented for [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") objects.

update(\[_iterable-or-mapping_\])[¶](https://docs.python.org/3/library/collections.html#collections.Counter.update "Link to this definition")

Elements are counted from an _iterable_ or added-in from another _mapping_ (or counter). Like [`dict.update()`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict.update "dict.update") but adds counts instead of replacing them. Also, the _iterable_ is expected to be a sequence of elements, not a sequence of `(key, value)` pairs.

Counters support rich comparison operators for equality, subset, and superset relationships: `==`, `!=`, `<`, `<=`, `>`, `>=`. All of those tests treat missing elements as having zero counts so that `Counter(a=1) == Counter(a=1, b=0)` returns true.

Changed in version 3.10: Rich comparison operations were added.

Changed in version 3.10: In equality tests, missing elements are treated as having zero counts. Formerly, `Counter(a=3)` and `Counter(a=3, b=0)` were considered distinct.

Common patterns for working with [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") objects:

```
<span></span><span class="n">c</span><span class="o">.</span><span class="n">total</span><span class="p">()</span>                       <span class="c1"># total of all counts</span>
<span class="n">c</span><span class="o">.</span><span class="n">clear</span><span class="p">()</span>                       <span class="c1"># reset all counts</span>
<span class="nb">list</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>                         <span class="c1"># list unique elements</span>
<span class="nb">set</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>                          <span class="c1"># convert to a set</span>
<span class="nb">dict</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>                         <span class="c1"># convert to a regular dictionary</span>
<span class="n">c</span><span class="o">.</span><span class="n">items</span><span class="p">()</span>                       <span class="c1"># access the (elem, cnt) pairs</span>
<span class="n">Counter</span><span class="p">(</span><span class="nb">dict</span><span class="p">(</span><span class="n">list_of_pairs</span><span class="p">))</span>    <span class="c1"># convert from a list of (elem, cnt) pairs</span>
<span class="n">c</span><span class="o">.</span><span class="n">most_common</span><span class="p">()[:</span><span class="o">-</span><span class="n">n</span><span class="o">-</span><span class="mi">1</span><span class="p">:</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>       <span class="c1"># n least common elements</span>
<span class="o">+</span><span class="n">c</span>                              <span class="c1"># remove zero and negative counts</span>
```

Several mathematical operations are provided for combining [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") objects to produce multisets (counters that have counts greater than zero). Addition and subtraction combine counters by adding or subtracting the counts of corresponding elements. Intersection and union return the minimum and maximum of corresponding counts. Equality and inclusion compare corresponding counts. Each operation can accept inputs with signed counts, but the output will exclude results with counts of zero or less.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">a</span><span class="o">=</span><span class="mi">3</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">a</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">2</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">+</span> <span class="n">d</span>                       <span class="c1"># add two counters together:  c[x] + d[x]</span>
<span class="go">Counter({'a': 4, 'b': 3})</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">-</span> <span class="n">d</span>                       <span class="c1"># subtract (keeping only positive counts)</span>
<span class="go">Counter({'a': 2})</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">&amp;</span> <span class="n">d</span>                       <span class="c1"># intersection:  min(c[x], d[x])</span>
<span class="go">Counter({'a': 1, 'b': 1})</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">|</span> <span class="n">d</span>                       <span class="c1"># union:  max(c[x], d[x])</span>
<span class="go">Counter({'a': 3, 'b': 2})</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">==</span> <span class="n">d</span>                      <span class="c1"># equality:  c[x] == d[x]</span>
<span class="go">False</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">&lt;=</span> <span class="n">d</span>                      <span class="c1"># inclusion:  c[x] &lt;= d[x]</span>
<span class="go">False</span>
```

Unary addition and subtraction are shortcuts for adding an empty counter or subtracting from an empty counter.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">c</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">a</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span> <span class="n">b</span><span class="o">=-</span><span class="mi">4</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="o">+</span><span class="n">c</span>
<span class="go">Counter({'a': 2})</span>
<span class="gp">&gt;&gt;&gt; </span><span class="o">-</span><span class="n">c</span>
<span class="go">Counter({'b': 4})</span>
```

Added in version 3.3: Added support for unary plus, unary minus, and in-place multiset operations.

Note

Counters were primarily designed to work with positive integers to represent running counts; however, care was taken to not unnecessarily preclude use cases needing other types or negative values. To help with those use cases, this section documents the minimum range and type restrictions.

-   The [`Counter`](https://docs.python.org/3/library/collections.html#collections.Counter "collections.Counter") class itself is a dictionary subclass with no restrictions on its keys and values. The values are intended to be numbers representing counts, but you _could_ store anything in the value field.
    
-   The [`most_common()`](https://docs.python.org/3/library/collections.html#collections.Counter.most_common "collections.Counter.most_common") method requires only that the values be orderable.
    
-   For in-place operations such as `c[key] += 1`, the value type need only support addition and subtraction. So fractions, floats, and decimals would work and negative values are supported. The same is also true for [`update()`](https://docs.python.org/3/library/collections.html#collections.Counter.update "collections.Counter.update") and [`subtract()`](https://docs.python.org/3/library/collections.html#collections.Counter.subtract "collections.Counter.subtract") which allow negative and zero values for both inputs and outputs.
    
-   The multiset methods are designed only for use cases with positive values. The inputs may be negative or zero, but only outputs with positive values are created. There are no type restrictions, but the value type needs to support addition, subtraction, and comparison.
    
-   The [`elements()`](https://docs.python.org/3/library/collections.html#collections.Counter.elements "collections.Counter.elements") method requires integer counts. It ignores zero and negative counts.
    

See also

-   [Bag class](https://www.gnu.org/software/smalltalk/manual-base/html_node/Bag.html) in Smalltalk.
    
-   Wikipedia entry for [Multisets](https://en.wikipedia.org/wiki/Multiset).
    
-   [C++ multisets](http://www.java2s.com/Tutorial/Cpp/0380__set-multiset/Catalog0380__set-multiset.htm) tutorial with examples.
    
-   For mathematical operations on multisets and their use cases, see _Knuth, Donald. The Art of Computer Programming Volume II, Section 4.6.3, Exercise 19_.
    
-   To enumerate all distinct multisets of a given size over a given set of elements, see [`itertools.combinations_with_replacement()`](https://docs.python.org/3/library/collections.htmlitertools.html#itertools.combinations_with_replacement "itertools.combinations_with_replacement"):
    
    ```
    <span></span><span class="nb">map</span><span class="p">(</span><span class="n">Counter</span><span class="p">,</span> <span class="n">combinations_with_replacement</span><span class="p">(</span><span class="s1">'ABC'</span><span class="p">,</span> <span class="mi">2</span><span class="p">))</span> <span class="c1"># --&gt; AA AB AC BB BC CC</span>
    ```
    

## [`deque`](https://docs.python.org/3/library/collections.html#collections.deque "collections.deque") objects[¶](https://docs.python.org/3/library/collections.html#deque-objects "Link to this heading")

_class_ collections.deque(\[_iterable_\[, _maxlen_\]\])[¶](https://docs.python.org/3/library/collections.html#collections.deque "Link to this definition")

Returns a new deque object initialized left-to-right (using [`append()`](https://docs.python.org/3/library/collections.html#collections.deque.append "collections.deque.append")) with data from _iterable_. If _iterable_ is not specified, the new deque is empty.

Deques are a generalization of stacks and queues (the name is pronounced “deck” and is short for “double-ended queue”). Deques support thread-safe, memory efficient appends and pops from either side of the deque with approximately the same _O_(1) performance in either direction.

Though [`list`](https://docs.python.org/3/library/collections.htmlstdtypes.html#list "list") objects support similar operations, they are optimized for fast fixed-length operations and incur _O_(_n_) memory movement costs for `pop(0)` and `insert(0, v)` operations which change both the size and position of the underlying data representation.

If _maxlen_ is not specified or is `None`, deques may grow to an arbitrary length. Otherwise, the deque is bounded to the specified maximum length. Once a bounded length deque is full, when new items are added, a corresponding number of items are discarded from the opposite end. Bounded length deques provide functionality similar to the `tail` filter in Unix. They are also useful for tracking transactions and other pools of data where only the most recent activity is of interest.

Deque objects support the following methods:

append(_x_)[¶](https://docs.python.org/3/library/collections.html#collections.deque.append "Link to this definition")

Add _x_ to the right side of the deque.

appendleft(_x_)[¶](https://docs.python.org/3/library/collections.html#collections.deque.appendleft "Link to this definition")

Add _x_ to the left side of the deque.

clear()[¶](https://docs.python.org/3/library/collections.html#collections.deque.clear "Link to this definition")

Remove all elements from the deque leaving it with length 0.

copy()[¶](https://docs.python.org/3/library/collections.html#collections.deque.copy "Link to this definition")

Create a shallow copy of the deque.

Added in version 3.5.

count(_x_)[¶](https://docs.python.org/3/library/collections.html#collections.deque.count "Link to this definition")

Count the number of deque elements equal to _x_.

Added in version 3.2.

extend(_iterable_)[¶](https://docs.python.org/3/library/collections.html#collections.deque.extend "Link to this definition")

Extend the right side of the deque by appending elements from the iterable argument.

extendleft(_iterable_)[¶](https://docs.python.org/3/library/collections.html#collections.deque.extendleft "Link to this definition")

Extend the left side of the deque by appending elements from _iterable_. Note, the series of left appends results in reversing the order of elements in the iterable argument.

index(_x_\[, _start_\[, _stop_\]\])[¶](https://docs.python.org/3/library/collections.html#collections.deque.index "Link to this definition")

Return the position of _x_ in the deque (at or after index _start_ and before index _stop_). Returns the first match or raises [`ValueError`](https://docs.python.org/3/library/collections.htmlexceptions.html#ValueError "ValueError") if not found.

Added in version 3.5.

insert(_i_, _x_)[¶](https://docs.python.org/3/library/collections.html#collections.deque.insert "Link to this definition")

Insert _x_ into the deque at position _i_.

If the insertion would cause a bounded deque to grow beyond _maxlen_, an [`IndexError`](https://docs.python.org/3/library/collections.htmlexceptions.html#IndexError "IndexError") is raised.

Added in version 3.5.

pop()[¶](https://docs.python.org/3/library/collections.html#collections.deque.pop "Link to this definition")

Remove and return an element from the right side of the deque. If no elements are present, raises an [`IndexError`](https://docs.python.org/3/library/collections.htmlexceptions.html#IndexError "IndexError").

popleft()[¶](https://docs.python.org/3/library/collections.html#collections.deque.popleft "Link to this definition")

Remove and return an element from the left side of the deque. If no elements are present, raises an [`IndexError`](https://docs.python.org/3/library/collections.htmlexceptions.html#IndexError "IndexError").

remove(_value_)[¶](https://docs.python.org/3/library/collections.html#collections.deque.remove "Link to this definition")

Remove the first occurrence of _value_. If not found, raises a [`ValueError`](https://docs.python.org/3/library/collections.htmlexceptions.html#ValueError "ValueError").

reverse()[¶](https://docs.python.org/3/library/collections.html#collections.deque.reverse "Link to this definition")

Reverse the elements of the deque in-place and then return `None`.

Added in version 3.2.

rotate(_n\=1_)[¶](https://docs.python.org/3/library/collections.html#collections.deque.rotate "Link to this definition")

Rotate the deque _n_ steps to the right. If _n_ is negative, rotate to the left.

When the deque is not empty, rotating one step to the right is equivalent to `d.appendleft(d.pop())`, and rotating one step to the left is equivalent to `d.append(d.popleft())`.

Deque objects also provide one read-only attribute:

maxlen[¶](https://docs.python.org/3/library/collections.html#collections.deque.maxlen "Link to this definition")

Maximum size of a deque or `None` if unbounded.

Added in version 3.1.

In addition to the above, deques support iteration, pickling, `len(d)`, `reversed(d)`, `copy.copy(d)`, `copy.deepcopy(d)`, membership testing with the [`in`](https://docs.python.org/3/library/collections.html../reference/expressions.html#in) operator, and subscript references such as `d[0]` to access the first element. Indexed access is _O_(1) at both ends but slows to _O_(_n_) in the middle. For fast random access, use lists instead.

Starting in version 3.5, deques support `__add__()`, `__mul__()`, and `__imul__()`.

Example:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="kn">from</span><span class="w"> </span><span class="nn">collections</span><span class="w"> </span><span class="kn">import</span> <span class="n">deque</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="n">deque</span><span class="p">(</span><span class="s1">'ghi'</span><span class="p">)</span>                 <span class="c1"># make a new deque with three items</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">elem</span> <span class="ow">in</span> <span class="n">d</span><span class="p">:</span>                   <span class="c1"># iterate over the deque's elements</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="n">elem</span><span class="o">.</span><span class="n">upper</span><span class="p">())</span>
<span class="go">G</span>
<span class="go">H</span>
<span class="go">I</span>

<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s1">'j'</span><span class="p">)</span>                    <span class="c1"># add a new entry to the right side</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">appendleft</span><span class="p">(</span><span class="s1">'f'</span><span class="p">)</span>                <span class="c1"># add a new entry to the left side</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span>                                <span class="c1"># show the representation of the deque</span>
<span class="go">deque(['f', 'g', 'h', 'i', 'j'])</span>

<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">pop</span><span class="p">()</span>                          <span class="c1"># return and remove the rightmost item</span>
<span class="go">'j'</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">popleft</span><span class="p">()</span>                      <span class="c1"># return and remove the leftmost item</span>
<span class="go">'f'</span>
<span class="gp">&gt;&gt;&gt; </span><span class="nb">list</span><span class="p">(</span><span class="n">d</span><span class="p">)</span>                          <span class="c1"># list the contents of the deque</span>
<span class="go">['g', 'h', 'i']</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>                             <span class="c1"># peek at leftmost item</span>
<span class="go">'g'</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>                            <span class="c1"># peek at rightmost item</span>
<span class="go">'i'</span>

<span class="gp">&gt;&gt;&gt; </span><span class="nb">list</span><span class="p">(</span><span class="nb">reversed</span><span class="p">(</span><span class="n">d</span><span class="p">))</span>                <span class="c1"># list the contents of a deque in reverse</span>
<span class="go">['i', 'h', 'g']</span>
<span class="gp">&gt;&gt;&gt; </span><span class="s1">'h'</span> <span class="ow">in</span> <span class="n">d</span>                         <span class="c1"># search the deque</span>
<span class="go">True</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">extend</span><span class="p">(</span><span class="s1">'jkl'</span><span class="p">)</span>                  <span class="c1"># add multiple elements at once</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span>
<span class="go">deque(['g', 'h', 'i', 'j', 'k', 'l'])</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">rotate</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>                      <span class="c1"># right rotation</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span>
<span class="go">deque(['l', 'g', 'h', 'i', 'j', 'k'])</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">rotate</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">)</span>                     <span class="c1"># left rotation</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span>
<span class="go">deque(['g', 'h', 'i', 'j', 'k', 'l'])</span>

<span class="gp">&gt;&gt;&gt; </span><span class="n">deque</span><span class="p">(</span><span class="nb">reversed</span><span class="p">(</span><span class="n">d</span><span class="p">))</span>               <span class="c1"># make a new deque in reverse order</span>
<span class="go">deque(['l', 'k', 'j', 'i', 'h', 'g'])</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">clear</span><span class="p">()</span>                        <span class="c1"># empty the deque</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">pop</span><span class="p">()</span>                          <span class="c1"># cannot pop from an empty deque</span>
<span class="gt">Traceback (most recent call last):</span>
<span class="w">    </span><span class="n">File</span> <span class="s2">"&lt;pyshell#6&gt;"</span><span class="p">,</span> <span class="n">line</span> <span class="mi">1</span><span class="p">,</span> <span class="ow">in</span> <span class="o">-</span><span class="n">toplevel</span><span class="o">-</span>
<span class="w">    </span>    <span class="n">d</span><span class="o">.</span><span class="n">pop</span><span class="p">()</span>
<span class="gr">IndexError</span>: <span class="n">pop from an empty deque</span>

<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">extendleft</span><span class="p">(</span><span class="s1">'abc'</span><span class="p">)</span>              <span class="c1"># extendleft() reverses the input order</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span>
<span class="go">deque(['c', 'b', 'a'])</span>
```

### [`deque`](https://docs.python.org/3/library/collections.html#collections.deque "collections.deque") Recipes[¶](https://docs.python.org/3/library/collections.html#deque-recipes "Link to this heading")

This section shows various approaches to working with deques.

Bounded length deques provide functionality similar to the `tail` filter in Unix:

```
<span></span><span class="k">def</span><span class="w"> </span><span class="nf">tail</span><span class="p">(</span><span class="n">filename</span><span class="p">,</span> <span class="n">n</span><span class="o">=</span><span class="mi">10</span><span class="p">):</span>
    <span class="s1">'Return the last n lines of a file'</span>
    <span class="k">with</span> <span class="nb">open</span><span class="p">(</span><span class="n">filename</span><span class="p">)</span> <span class="k">as</span> <span class="n">f</span><span class="p">:</span>
        <span class="k">return</span> <span class="n">deque</span><span class="p">(</span><span class="n">f</span><span class="p">,</span> <span class="n">n</span><span class="p">)</span>
```

Another approach to using deques is to maintain a sequence of recently added elements by appending to the right and popping to the left:

```
<span></span><span class="k">def</span><span class="w"> </span><span class="nf">moving_average</span><span class="p">(</span><span class="n">iterable</span><span class="p">,</span> <span class="n">n</span><span class="o">=</span><span class="mi">3</span><span class="p">):</span>
    <span class="c1"># moving_average([40, 30, 50, 46, 39, 44]) --&gt; 40.0 42.0 45.0 43.0</span>
    <span class="c1"># https://en.wikipedia.org/wiki/Moving_average</span>
    <span class="n">it</span> <span class="o">=</span> <span class="nb">iter</span><span class="p">(</span><span class="n">iterable</span><span class="p">)</span>
    <span class="n">d</span> <span class="o">=</span> <span class="n">deque</span><span class="p">(</span><span class="n">itertools</span><span class="o">.</span><span class="n">islice</span><span class="p">(</span><span class="n">it</span><span class="p">,</span> <span class="n">n</span><span class="o">-</span><span class="mi">1</span><span class="p">))</span>
    <span class="n">d</span><span class="o">.</span><span class="n">appendleft</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
    <span class="n">s</span> <span class="o">=</span> <span class="nb">sum</span><span class="p">(</span><span class="n">d</span><span class="p">)</span>
    <span class="k">for</span> <span class="n">elem</span> <span class="ow">in</span> <span class="n">it</span><span class="p">:</span>
        <span class="n">s</span> <span class="o">+=</span> <span class="n">elem</span> <span class="o">-</span> <span class="n">d</span><span class="o">.</span><span class="n">popleft</span><span class="p">()</span>
        <span class="n">d</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">elem</span><span class="p">)</span>
        <span class="k">yield</span> <span class="n">s</span> <span class="o">/</span> <span class="n">n</span>
```

A [round-robin scheduler](https://en.wikipedia.org/wiki/Round-robin_scheduling) can be implemented with input iterators stored in a [`deque`](https://docs.python.org/3/library/collections.html#collections.deque "collections.deque"). Values are yielded from the active iterator in position zero. If that iterator is exhausted, it can be removed with [`popleft()`](https://docs.python.org/3/library/collections.html#collections.deque.popleft "collections.deque.popleft"); otherwise, it can be cycled back to the end with the [`rotate()`](https://docs.python.org/3/library/collections.html#collections.deque.rotate "collections.deque.rotate") method:

```
<span></span><span class="k">def</span><span class="w"> </span><span class="nf">roundrobin</span><span class="p">(</span><span class="o">*</span><span class="n">iterables</span><span class="p">):</span>
    <span class="s2">"roundrobin('ABC', 'D', 'EF') --&gt; A D E B F C"</span>
    <span class="n">iterators</span> <span class="o">=</span> <span class="n">deque</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">iter</span><span class="p">,</span> <span class="n">iterables</span><span class="p">))</span>
    <span class="k">while</span> <span class="n">iterators</span><span class="p">:</span>
        <span class="k">try</span><span class="p">:</span>
            <span class="k">while</span> <span class="kc">True</span><span class="p">:</span>
                <span class="k">yield</span> <span class="nb">next</span><span class="p">(</span><span class="n">iterators</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
                <span class="n">iterators</span><span class="o">.</span><span class="n">rotate</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">)</span>
        <span class="k">except</span> <span class="ne">StopIteration</span><span class="p">:</span>
            <span class="c1"># Remove an exhausted iterator.</span>
            <span class="n">iterators</span><span class="o">.</span><span class="n">popleft</span><span class="p">()</span>
```

The [`rotate()`](https://docs.python.org/3/library/collections.html#collections.deque.rotate "collections.deque.rotate") method provides a way to implement [`deque`](https://docs.python.org/3/library/collections.html#collections.deque "collections.deque") slicing and deletion. For example, a pure Python implementation of `del d[n]` relies on the `rotate()` method to position elements to be popped:

```
<span></span><span class="k">def</span><span class="w"> </span><span class="nf">delete_nth</span><span class="p">(</span><span class="n">d</span><span class="p">,</span> <span class="n">n</span><span class="p">):</span>
    <span class="n">d</span><span class="o">.</span><span class="n">rotate</span><span class="p">(</span><span class="o">-</span><span class="n">n</span><span class="p">)</span>
    <span class="n">d</span><span class="o">.</span><span class="n">popleft</span><span class="p">()</span>
    <span class="n">d</span><span class="o">.</span><span class="n">rotate</span><span class="p">(</span><span class="n">n</span><span class="p">)</span>
```

To implement [`deque`](https://docs.python.org/3/library/collections.html#collections.deque "collections.deque") slicing, use a similar approach applying [`rotate()`](https://docs.python.org/3/library/collections.html#collections.deque.rotate "collections.deque.rotate") to bring a target element to the left side of the deque. Remove old entries with [`popleft()`](https://docs.python.org/3/library/collections.html#collections.deque.popleft "collections.deque.popleft"), add new entries with [`extend()`](https://docs.python.org/3/library/collections.html#collections.deque.extend "collections.deque.extend"), and then reverse the rotation. With minor variations on that approach, it is easy to implement Forth style stack manipulations such as `dup`, `drop`, `swap`, `over`, `pick`, `rot`, and `roll`.

## [`defaultdict`](https://docs.python.org/3/library/collections.html#collections.defaultdict "collections.defaultdict") objects[¶](https://docs.python.org/3/library/collections.html#defaultdict-objects "Link to this heading")

_class_ collections.defaultdict(_default\_factory=None_, _/_\[, _..._\])[¶](https://docs.python.org/3/library/collections.html#collections.defaultdict "Link to this definition")

Return a new dictionary-like object. [`defaultdict`](https://docs.python.org/3/library/collections.html#collections.defaultdict "collections.defaultdict") is a subclass of the built-in [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") class. It overrides one method and adds one writable instance variable. The remaining functionality is the same as for the [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") class and is not documented here.

The first argument provides the initial value for the [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory") attribute; it defaults to `None`. All remaining arguments are treated the same as if they were passed to the [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") constructor, including keyword arguments.

[`defaultdict`](https://docs.python.org/3/library/collections.html#collections.defaultdict "collections.defaultdict") objects support the following method in addition to the standard [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") operations:

\_\_missing\_\_(_key_)[¶](https://docs.python.org/3/library/collections.html#collections.defaultdict.__missing__ "Link to this definition")

If the [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory") attribute is `None`, this raises a [`KeyError`](https://docs.python.org/3/library/collections.htmlexceptions.html#KeyError "KeyError") exception with the _key_ as argument.

If [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory") is not `None`, it is called without arguments to provide a default value for the given _key_, this value is inserted in the dictionary for the _key_, and returned.

If calling [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory") raises an exception this exception is propagated unchanged.

This method is called by the [`__getitem__()`](https://docs.python.org/3/library/collections.html../reference/datamodel.html#object.__getitem__ "object.__getitem__") method of the [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") class when the requested key is not found; whatever it returns or raises is then returned or raised by [`__getitem__()`](https://docs.python.org/3/library/collections.html../reference/datamodel.html#object.__getitem__ "object.__getitem__").

Note that [`__missing__()`](https://docs.python.org/3/library/collections.html#collections.defaultdict.__missing__ "collections.defaultdict.__missing__") is _not_ called for any operations besides [`__getitem__()`](https://docs.python.org/3/library/collections.html../reference/datamodel.html#object.__getitem__ "object.__getitem__"). This means that `get()` will, like normal dictionaries, return `None` as a default rather than using [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory").

[`defaultdict`](https://docs.python.org/3/library/collections.html#collections.defaultdict "collections.defaultdict") objects support the following instance variable:

default\_factory[¶](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "Link to this definition")

This attribute is used by the [`__missing__()`](https://docs.python.org/3/library/collections.html#collections.defaultdict.__missing__ "collections.defaultdict.__missing__") method; it is initialized from the first argument to the constructor, if present, or to `None`, if absent.

Changed in version 3.9: Added merge (`|`) and update (`|=`) operators, specified in [**PEP 584**](https://peps.python.org/pep-0584/).

### [`defaultdict`](https://docs.python.org/3/library/collections.html#collections.defaultdict "collections.defaultdict") Examples[¶](https://docs.python.org/3/library/collections.html#defaultdict-examples "Link to this heading")

Using [`list`](https://docs.python.org/3/library/collections.htmlstdtypes.html#list "list") as the [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory"), it is easy to group a sequence of key-value pairs into a dictionary of lists:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">s</span> <span class="o">=</span> <span class="p">[(</span><span class="s1">'yellow'</span><span class="p">,</span> <span class="mi">1</span><span class="p">),</span> <span class="p">(</span><span class="s1">'blue'</span><span class="p">,</span> <span class="mi">2</span><span class="p">),</span> <span class="p">(</span><span class="s1">'yellow'</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="p">(</span><span class="s1">'blue'</span><span class="p">,</span> <span class="mi">4</span><span class="p">),</span> <span class="p">(</span><span class="s1">'red'</span><span class="p">,</span> <span class="mi">1</span><span class="p">)]</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="n">defaultdict</span><span class="p">(</span><span class="nb">list</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">k</span><span class="p">,</span> <span class="n">v</span> <span class="ow">in</span> <span class="n">s</span><span class="p">:</span>
<span class="gp">... </span>    <span class="n">d</span><span class="p">[</span><span class="n">k</span><span class="p">]</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">v</span><span class="p">)</span>
<span class="gp">...</span>
<span class="gp">&gt;&gt;&gt; </span><span class="nb">sorted</span><span class="p">(</span><span class="n">d</span><span class="o">.</span><span class="n">items</span><span class="p">())</span>
<span class="go">[('blue', [2, 4]), ('red', [1]), ('yellow', [1, 3])]</span>
```

When each key is encountered for the first time, it is not already in the mapping; so an entry is automatically created using the [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory") function which returns an empty [`list`](https://docs.python.org/3/library/collections.htmlstdtypes.html#list "list"). The `list.append()` operation then attaches the value to the new list. When keys are encountered again, the look-up proceeds normally (returning the list for that key) and the `list.append()` operation adds another value to the list. This technique is simpler and faster than an equivalent technique using [`dict.setdefault()`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict.setdefault "dict.setdefault"):

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="p">{}</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">k</span><span class="p">,</span> <span class="n">v</span> <span class="ow">in</span> <span class="n">s</span><span class="p">:</span>
<span class="gp">... </span>    <span class="n">d</span><span class="o">.</span><span class="n">setdefault</span><span class="p">(</span><span class="n">k</span><span class="p">,</span> <span class="p">[])</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">v</span><span class="p">)</span>
<span class="gp">...</span>
<span class="gp">&gt;&gt;&gt; </span><span class="nb">sorted</span><span class="p">(</span><span class="n">d</span><span class="o">.</span><span class="n">items</span><span class="p">())</span>
<span class="go">[('blue', [2, 4]), ('red', [1]), ('yellow', [1, 3])]</span>
```

Setting the [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory") to [`int`](https://docs.python.org/3/library/collections.htmlfunctions.html#int "int") makes the [`defaultdict`](https://docs.python.org/3/library/collections.html#collections.defaultdict "collections.defaultdict") useful for counting (like a bag or multiset in other languages):

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">s</span> <span class="o">=</span> <span class="s1">'mississippi'</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="n">defaultdict</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">k</span> <span class="ow">in</span> <span class="n">s</span><span class="p">:</span>
<span class="gp">... </span>    <span class="n">d</span><span class="p">[</span><span class="n">k</span><span class="p">]</span> <span class="o">+=</span> <span class="mi">1</span>
<span class="gp">...</span>
<span class="gp">&gt;&gt;&gt; </span><span class="nb">sorted</span><span class="p">(</span><span class="n">d</span><span class="o">.</span><span class="n">items</span><span class="p">())</span>
<span class="go">[('i', 4), ('m', 1), ('p', 2), ('s', 4)]</span>
```

When a letter is first encountered, it is missing from the mapping, so the [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory") function calls [`int()`](https://docs.python.org/3/library/collections.htmlfunctions.html#int "int") to supply a default count of zero. The increment operation then builds up the count for each letter.

The function [`int()`](https://docs.python.org/3/library/collections.htmlfunctions.html#int "int") which always returns zero is just a special case of constant functions. A faster and more flexible way to create constant functions is to use a lambda function which can supply any constant value (not just zero):

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="k">def</span><span class="w"> </span><span class="nf">constant_factory</span><span class="p">(</span><span class="n">value</span><span class="p">):</span>
<span class="gp">... </span>    <span class="k">return</span> <span class="k">lambda</span><span class="p">:</span> <span class="n">value</span>
<span class="gp">...</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="n">defaultdict</span><span class="p">(</span><span class="n">constant_factory</span><span class="p">(</span><span class="s1">'&lt;missing&gt;'</span><span class="p">))</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">update</span><span class="p">(</span><span class="n">name</span><span class="o">=</span><span class="s1">'John'</span><span class="p">,</span> <span class="n">action</span><span class="o">=</span><span class="s1">'ran'</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="s1">'</span><span class="si">%(name)s</span><span class="s1"> </span><span class="si">%(action)s</span><span class="s1"> to </span><span class="si">%(object)s</span><span class="s1">'</span> <span class="o">%</span> <span class="n">d</span>
<span class="go">'John ran to &lt;missing&gt;'</span>
```

Setting the [`default_factory`](https://docs.python.org/3/library/collections.html#collections.defaultdict.default_factory "collections.defaultdict.default_factory") to [`set`](https://docs.python.org/3/library/collections.htmlstdtypes.html#set "set") makes the [`defaultdict`](https://docs.python.org/3/library/collections.html#collections.defaultdict "collections.defaultdict") useful for building a dictionary of sets:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">s</span> <span class="o">=</span> <span class="p">[(</span><span class="s1">'red'</span><span class="p">,</span> <span class="mi">1</span><span class="p">),</span> <span class="p">(</span><span class="s1">'blue'</span><span class="p">,</span> <span class="mi">2</span><span class="p">),</span> <span class="p">(</span><span class="s1">'red'</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="p">(</span><span class="s1">'blue'</span><span class="p">,</span> <span class="mi">4</span><span class="p">),</span> <span class="p">(</span><span class="s1">'red'</span><span class="p">,</span> <span class="mi">1</span><span class="p">),</span> <span class="p">(</span><span class="s1">'blue'</span><span class="p">,</span> <span class="mi">4</span><span class="p">)]</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="n">defaultdict</span><span class="p">(</span><span class="nb">set</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">k</span><span class="p">,</span> <span class="n">v</span> <span class="ow">in</span> <span class="n">s</span><span class="p">:</span>
<span class="gp">... </span>    <span class="n">d</span><span class="p">[</span><span class="n">k</span><span class="p">]</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">v</span><span class="p">)</span>
<span class="gp">...</span>
<span class="gp">&gt;&gt;&gt; </span><span class="nb">sorted</span><span class="p">(</span><span class="n">d</span><span class="o">.</span><span class="n">items</span><span class="p">())</span>
<span class="go">[('blue', {2, 4}), ('red', {1, 3})]</span>
```

## [`namedtuple()`](https://docs.python.org/3/library/collections.html#collections.namedtuple "collections.namedtuple") Factory Function for Tuples with Named Fields[¶](https://docs.python.org/3/library/collections.html#namedtuple-factory-function-for-tuples-with-named-fields "Link to this heading")

Named tuples assign meaning to each position in a tuple and allow for more readable, self-documenting code. They can be used wherever regular tuples are used, and they add the ability to access fields by name instead of position index.

collections.namedtuple(_typename_, _field\_names_, _\*_, _rename\=False_, _defaults\=None_, _module\=None_)[¶](https://docs.python.org/3/library/collections.html#collections.namedtuple "Link to this definition")

Returns a new tuple subclass named _typename_. The new subclass is used to create tuple-like objects that have fields accessible by attribute lookup as well as being indexable and iterable. Instances of the subclass also have a helpful docstring (with typename and field\_names) and a helpful `__repr__()` method which lists the tuple contents in a `name=value` format.

The _field\_names_ are a sequence of strings such as `['x', 'y']`. Alternatively, _field\_names_ can be a single string with each fieldname separated by whitespace and/or commas, for example `'x y'` or `'x, y'`.

Any valid Python identifier may be used for a fieldname except for names starting with an underscore. Valid identifiers consist of letters, digits, and underscores but do not start with a digit or underscore and cannot be a [`keyword`](https://docs.python.org/3/library/collections.htmlkeyword.html#module-keyword "keyword: Test whether a string is a keyword in Python.") such as _class_, _for_, _return_, _global_, _pass_, or _raise_.

If _rename_ is true, invalid fieldnames are automatically replaced with positional names. For example, `['abc', 'def', 'ghi', 'abc']` is converted to `['abc', '_1', 'ghi', '_3']`, eliminating the keyword `def` and the duplicate fieldname `abc`.

_defaults_ can be `None` or an [iterable](https://docs.python.org/3/library/collections.html../glossary.html#term-iterable) of default values. Since fields with a default value must come after any fields without a default, the _defaults_ are applied to the rightmost parameters. For example, if the fieldnames are `['x', 'y', 'z']` and the defaults are `(1, 2)`, then `x` will be a required argument, `y` will default to `1`, and `z` will default to `2`.

If _module_ is defined, the [`__module__`](https://docs.python.org/3/library/collections.html../reference/datamodel.html#type.__module__ "type.__module__") attribute of the named tuple is set to that value.

Named tuple instances do not have per-instance dictionaries, so they are lightweight and require no more memory than regular tuples.

To support pickling, the named tuple class should be assigned to a variable that matches _typename_.

Changed in version 3.1: Added support for _rename_.

Changed in version 3.6: The _verbose_ and _rename_ parameters became [keyword-only arguments](https://docs.python.org/3/library/collections.html../glossary.html#keyword-only-parameter).

Changed in version 3.6: Added the _module_ parameter.

Changed in version 3.7: Removed the _verbose_ parameter and the `_source` attribute.

Changed in version 3.7: Added the _defaults_ parameter and the `_field_defaults` attribute.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="c1"># Basic example</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Point</span> <span class="o">=</span> <span class="n">namedtuple</span><span class="p">(</span><span class="s1">'Point'</span><span class="p">,</span> <span class="p">[</span><span class="s1">'x'</span><span class="p">,</span> <span class="s1">'y'</span><span class="p">])</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">p</span> <span class="o">=</span> <span class="n">Point</span><span class="p">(</span><span class="mi">11</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="mi">22</span><span class="p">)</span>     <span class="c1"># instantiate with positional or keyword arguments</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">p</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">+</span> <span class="n">p</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span>             <span class="c1"># indexable like the plain tuple (11, 22)</span>
<span class="go">33</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">x</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="n">p</span>                <span class="c1"># unpack like a regular tuple</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">x</span><span class="p">,</span> <span class="n">y</span>
<span class="go">(11, 22)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">p</span><span class="o">.</span><span class="n">x</span> <span class="o">+</span> <span class="n">p</span><span class="o">.</span><span class="n">y</span>               <span class="c1"># fields also accessible by name</span>
<span class="go">33</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">p</span>                       <span class="c1"># readable __repr__ with a name=value style</span>
<span class="go">Point(x=11, y=22)</span>
```

Named tuples are especially useful for assigning field names to result tuples returned by the [`csv`](https://docs.python.org/3/library/collections.htmlcsv.html#module-csv "csv: Write and read tabular data to and from delimited files.") or [`sqlite3`](https://docs.python.org/3/library/collections.htmlsqlite3.html#module-sqlite3 "sqlite3: A DB-API 2.0 implementation using SQLite 3.x.") modules:

```
<span></span><span class="n">EmployeeRecord</span> <span class="o">=</span> <span class="n">namedtuple</span><span class="p">(</span><span class="s1">'EmployeeRecord'</span><span class="p">,</span> <span class="s1">'name, age, title, department, paygrade'</span><span class="p">)</span>

<span class="kn">import</span><span class="w"> </span><span class="nn">csv</span>
<span class="k">for</span> <span class="n">emp</span> <span class="ow">in</span> <span class="nb">map</span><span class="p">(</span><span class="n">EmployeeRecord</span><span class="o">.</span><span class="n">_make</span><span class="p">,</span> <span class="n">csv</span><span class="o">.</span><span class="n">reader</span><span class="p">(</span><span class="nb">open</span><span class="p">(</span><span class="s2">"employees.csv"</span><span class="p">,</span> <span class="s2">"rb"</span><span class="p">))):</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">emp</span><span class="o">.</span><span class="n">name</span><span class="p">,</span> <span class="n">emp</span><span class="o">.</span><span class="n">title</span><span class="p">)</span>

<span class="kn">import</span><span class="w"> </span><span class="nn">sqlite3</span>
<span class="n">conn</span> <span class="o">=</span> <span class="n">sqlite3</span><span class="o">.</span><span class="n">connect</span><span class="p">(</span><span class="s1">'/companydata'</span><span class="p">)</span>
<span class="n">cursor</span> <span class="o">=</span> <span class="n">conn</span><span class="o">.</span><span class="n">cursor</span><span class="p">()</span>
<span class="n">cursor</span><span class="o">.</span><span class="n">execute</span><span class="p">(</span><span class="s1">'SELECT name, age, title, department, paygrade FROM employees'</span><span class="p">)</span>
<span class="k">for</span> <span class="n">emp</span> <span class="ow">in</span> <span class="nb">map</span><span class="p">(</span><span class="n">EmployeeRecord</span><span class="o">.</span><span class="n">_make</span><span class="p">,</span> <span class="n">cursor</span><span class="o">.</span><span class="n">fetchall</span><span class="p">()):</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">emp</span><span class="o">.</span><span class="n">name</span><span class="p">,</span> <span class="n">emp</span><span class="o">.</span><span class="n">title</span><span class="p">)</span>
```

In addition to the methods inherited from tuples, named tuples support three additional methods and two attributes. To prevent conflicts with field names, the method and attribute names start with an underscore.

_classmethod_ somenamedtuple.\_make(_iterable_)[¶](https://docs.python.org/3/library/collections.html#collections.somenamedtuple._make "Link to this definition")

Class method that makes a new instance from an existing sequence or iterable.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">t</span> <span class="o">=</span> <span class="p">[</span><span class="mi">11</span><span class="p">,</span> <span class="mi">22</span><span class="p">]</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Point</span><span class="o">.</span><span class="n">_make</span><span class="p">(</span><span class="n">t</span><span class="p">)</span>
<span class="go">Point(x=11, y=22)</span>
```

somenamedtuple.\_asdict()[¶](https://docs.python.org/3/library/collections.html#collections.somenamedtuple._asdict "Link to this definition")

Return a new [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") which maps field names to their corresponding values:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">p</span> <span class="o">=</span> <span class="n">Point</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="mi">11</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="mi">22</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">p</span><span class="o">.</span><span class="n">_asdict</span><span class="p">()</span>
<span class="go">{'x': 11, 'y': 22}</span>
```

Changed in version 3.1: Returns an [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") instead of a regular [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict").

Changed in version 3.8: Returns a regular [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") instead of an [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict"). As of Python 3.7, regular dicts are guaranteed to be ordered. If the extra features of [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") are required, the suggested remediation is to cast the result to the desired type: `OrderedDict(nt._asdict())`.

somenamedtuple.\_replace(_\*\*kwargs_)[¶](https://docs.python.org/3/library/collections.html#collections.somenamedtuple._replace "Link to this definition")

Return a new instance of the named tuple replacing specified fields with new values:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">p</span> <span class="o">=</span> <span class="n">Point</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="mi">11</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="mi">22</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">p</span><span class="o">.</span><span class="n">_replace</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="mi">33</span><span class="p">)</span>
<span class="go">Point(x=33, y=22)</span>

<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">partnum</span><span class="p">,</span> <span class="n">record</span> <span class="ow">in</span> <span class="n">inventory</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>
<span class="gp">... </span>    <span class="n">inventory</span><span class="p">[</span><span class="n">partnum</span><span class="p">]</span> <span class="o">=</span> <span class="n">record</span><span class="o">.</span><span class="n">_replace</span><span class="p">(</span><span class="n">price</span><span class="o">=</span><span class="n">newprices</span><span class="p">[</span><span class="n">partnum</span><span class="p">],</span> <span class="n">timestamp</span><span class="o">=</span><span class="n">time</span><span class="o">.</span><span class="n">now</span><span class="p">())</span>
```

Named tuples are also supported by generic function [`copy.replace()`](https://docs.python.org/3/library/collections.htmlcopy.html#copy.replace "copy.replace").

Changed in version 3.13: Raise [`TypeError`](https://docs.python.org/3/library/collections.htmlexceptions.html#TypeError "TypeError") instead of [`ValueError`](https://docs.python.org/3/library/collections.htmlexceptions.html#ValueError "ValueError") for invalid keyword arguments.

somenamedtuple.\_fields[¶](https://docs.python.org/3/library/collections.html#collections.somenamedtuple._fields "Link to this definition")

Tuple of strings listing the field names. Useful for introspection and for creating new named tuple types from existing named tuples.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">p</span><span class="o">.</span><span class="n">_fields</span>            <span class="c1"># view the field names</span>
<span class="go">('x', 'y')</span>

<span class="gp">&gt;&gt;&gt; </span><span class="n">Color</span> <span class="o">=</span> <span class="n">namedtuple</span><span class="p">(</span><span class="s1">'Color'</span><span class="p">,</span> <span class="s1">'red green blue'</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Pixel</span> <span class="o">=</span> <span class="n">namedtuple</span><span class="p">(</span><span class="s1">'Pixel'</span><span class="p">,</span> <span class="n">Point</span><span class="o">.</span><span class="n">_fields</span> <span class="o">+</span> <span class="n">Color</span><span class="o">.</span><span class="n">_fields</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Pixel</span><span class="p">(</span><span class="mi">11</span><span class="p">,</span> <span class="mi">22</span><span class="p">,</span> <span class="mi">128</span><span class="p">,</span> <span class="mi">255</span><span class="p">,</span> <span class="mi">0</span><span class="p">)</span>
<span class="go">Pixel(x=11, y=22, red=128, green=255, blue=0)</span>
```

somenamedtuple.\_field\_defaults[¶](https://docs.python.org/3/library/collections.html#collections.somenamedtuple._field_defaults "Link to this definition")

Dictionary mapping field names to default values.

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">Account</span> <span class="o">=</span> <span class="n">namedtuple</span><span class="p">(</span><span class="s1">'Account'</span><span class="p">,</span> <span class="p">[</span><span class="s1">'type'</span><span class="p">,</span> <span class="s1">'balance'</span><span class="p">],</span> <span class="n">defaults</span><span class="o">=</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Account</span><span class="o">.</span><span class="n">_field_defaults</span>
<span class="go">{'balance': 0}</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Account</span><span class="p">(</span><span class="s1">'premium'</span><span class="p">)</span>
<span class="go">Account(type='premium', balance=0)</span>
```

To retrieve a field whose name is stored in a string, use the [`getattr()`](https://docs.python.org/3/library/collections.htmlfunctions.html#getattr "getattr") function:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="nb">getattr</span><span class="p">(</span><span class="n">p</span><span class="p">,</span> <span class="s1">'x'</span><span class="p">)</span>
<span class="go">11</span>
```

To convert a dictionary to a named tuple, use the double-star-operator (as described in [Unpacking Argument Lists](https://docs.python.org/3/library/collections.html../tutorial/controlflow.html#tut-unpacking-arguments)):

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'x'</span><span class="p">:</span> <span class="mi">11</span><span class="p">,</span> <span class="s1">'y'</span><span class="p">:</span> <span class="mi">22</span><span class="p">}</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Point</span><span class="p">(</span><span class="o">**</span><span class="n">d</span><span class="p">)</span>
<span class="go">Point(x=11, y=22)</span>
```

Since a named tuple is a regular Python class, it is easy to add or change functionality with a subclass. Here is how to add a calculated field and a fixed-width print format:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="k">class</span><span class="w"> </span><span class="nc">Point</span><span class="p">(</span><span class="n">namedtuple</span><span class="p">(</span><span class="s1">'Point'</span><span class="p">,</span> <span class="p">[</span><span class="s1">'x'</span><span class="p">,</span> <span class="s1">'y'</span><span class="p">])):</span>
<span class="gp">... </span>    <span class="vm">__slots__</span> <span class="o">=</span> <span class="p">()</span>
<span class="gp">... </span>    <span class="nd">@property</span>
<span class="gp">... </span>    <span class="k">def</span><span class="w"> </span><span class="nf">hypot</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
<span class="gp">... </span>        <span class="k">return</span> <span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">x</span> <span class="o">**</span> <span class="mi">2</span> <span class="o">+</span> <span class="bp">self</span><span class="o">.</span><span class="n">y</span> <span class="o">**</span> <span class="mi">2</span><span class="p">)</span> <span class="o">**</span> <span class="mf">0.5</span>
<span class="gp">... </span>    <span class="k">def</span><span class="w"> </span><span class="fm">__str__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
<span class="gp">... </span>        <span class="k">return</span> <span class="s1">'Point: x=</span><span class="si">%6.3f</span><span class="s1">  y=</span><span class="si">%6.3f</span><span class="s1">  hypot=</span><span class="si">%6.3f</span><span class="s1">'</span> <span class="o">%</span> <span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">x</span><span class="p">,</span> <span class="bp">self</span><span class="o">.</span><span class="n">y</span><span class="p">,</span> <span class="bp">self</span><span class="o">.</span><span class="n">hypot</span><span class="p">)</span>

<span class="gp">&gt;&gt;&gt; </span><span class="k">for</span> <span class="n">p</span> <span class="ow">in</span> <span class="n">Point</span><span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">4</span><span class="p">),</span> <span class="n">Point</span><span class="p">(</span><span class="mi">14</span><span class="p">,</span> <span class="mi">5</span><span class="o">/</span><span class="mi">7</span><span class="p">):</span>
<span class="gp">... </span>    <span class="nb">print</span><span class="p">(</span><span class="n">p</span><span class="p">)</span>
<span class="go">Point: x= 3.000  y= 4.000  hypot= 5.000</span>
<span class="go">Point: x=14.000  y= 0.714  hypot=14.018</span>
```

The subclass shown above sets `__slots__` to an empty tuple. This helps keep memory requirements low by preventing the creation of instance dictionaries.

Subclassing is not useful for adding new, stored fields. Instead, simply create a new named tuple type from the [`_fields`](https://docs.python.org/3/library/collections.html#collections.somenamedtuple._fields "collections.somenamedtuple._fields") attribute:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">Point3D</span> <span class="o">=</span> <span class="n">namedtuple</span><span class="p">(</span><span class="s1">'Point3D'</span><span class="p">,</span> <span class="n">Point</span><span class="o">.</span><span class="n">_fields</span> <span class="o">+</span> <span class="p">(</span><span class="s1">'z'</span><span class="p">,))</span>
```

Docstrings can be customized by making direct assignments to the `__doc__` fields:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">Book</span> <span class="o">=</span> <span class="n">namedtuple</span><span class="p">(</span><span class="s1">'Book'</span><span class="p">,</span> <span class="p">[</span><span class="s1">'id'</span><span class="p">,</span> <span class="s1">'title'</span><span class="p">,</span> <span class="s1">'authors'</span><span class="p">])</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Book</span><span class="o">.</span><span class="vm">__doc__</span> <span class="o">+=</span> <span class="s1">': Hardcover book in active collection'</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Book</span><span class="o">.</span><span class="n">id</span><span class="o">.</span><span class="vm">__doc__</span> <span class="o">=</span> <span class="s1">'13-digit ISBN'</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Book</span><span class="o">.</span><span class="n">title</span><span class="o">.</span><span class="vm">__doc__</span> <span class="o">=</span> <span class="s1">'Title of first printing'</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Book</span><span class="o">.</span><span class="n">authors</span><span class="o">.</span><span class="vm">__doc__</span> <span class="o">=</span> <span class="s1">'List of authors sorted by last name'</span>
```

Changed in version 3.5: Property docstrings became writeable.

See also

-   See [`typing.NamedTuple`](https://docs.python.org/3/library/collections.htmltyping.html#typing.NamedTuple "typing.NamedTuple") for a way to add type hints for named tuples. It also provides an elegant notation using the [`class`](https://docs.python.org/3/library/collections.html../reference/compound_stmts.html#class) keyword:
    
    ```
    <span></span><span class="k">class</span><span class="w"> </span><span class="nc">Component</span><span class="p">(</span><span class="n">NamedTuple</span><span class="p">):</span>
        <span class="n">part_number</span><span class="p">:</span> <span class="nb">int</span>
        <span class="n">weight</span><span class="p">:</span> <span class="nb">float</span>
        <span class="n">description</span><span class="p">:</span> <span class="n">Optional</span><span class="p">[</span><span class="nb">str</span><span class="p">]</span> <span class="o">=</span> <span class="kc">None</span>
    ```
    
-   See [`types.SimpleNamespace()`](https://docs.python.org/3/library/collections.htmltypes.html#types.SimpleNamespace "types.SimpleNamespace") for a mutable namespace based on an underlying dictionary instead of a tuple.
    
-   The [`dataclasses`](https://docs.python.org/3/library/collections.htmldataclasses.html#module-dataclasses "dataclasses: Generate special methods on user-defined classes.") module provides a decorator and functions for automatically adding generated special methods to user-defined classes.
    

## [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") objects[¶](https://docs.python.org/3/library/collections.html#ordereddict-objects "Link to this heading")

Ordered dictionaries are just like regular dictionaries but have some extra capabilities relating to ordering operations. They have become less important now that the built-in [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") class gained the ability to remember insertion order (this new behavior became guaranteed in Python 3.7).

Some differences from [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") still remain:

-   The regular [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") was designed to be very good at mapping operations. Tracking insertion order was secondary.
    
-   The [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") was designed to be good at reordering operations. Space efficiency, iteration speed, and the performance of update operations were secondary.
    
-   The [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") algorithm can handle frequent reordering operations better than [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict"). As shown in the recipes below, this makes it suitable for implementing various kinds of LRU caches.
    
-   The equality operation for [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") checks for matching order.
    
    A regular [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") can emulate the order sensitive equality test with `p == q and all(k1 == k2 for k1, k2 in zip(p, q))`.
    
-   The `popitem()` method of [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") has a different signature. It accepts an optional argument to specify which item is popped.
    
    A regular [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") can emulate OrderedDict’s `od.popitem(last=True)` with `d.popitem()` which is guaranteed to pop the rightmost (last) item.
    
    A regular [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") can emulate OrderedDict’s `od.popitem(last=False)` with `(k := next(iter(d)), d.pop(k))` which will return and remove the leftmost (first) item if it exists.
    
-   [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") has a `move_to_end()` method to efficiently reposition an element to an endpoint.
    
    A regular [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") can emulate OrderedDict’s `od.move_to_end(k, last=True)` with `d[k] = d.pop(k)` which will move the key and its associated value to the rightmost (last) position.
    
    A regular [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") does not have an efficient equivalent for OrderedDict’s `od.move_to_end(k, last=False)` which moves the key and its associated value to the leftmost (first) position.
    
-   Until Python 3.8, [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") lacked a `__reversed__()` method.
    

_class_ collections.OrderedDict(\[_items_\])[¶](https://docs.python.org/3/library/collections.html#collections.OrderedDict "Link to this definition")

Return an instance of a [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict") subclass that has methods specialized for rearranging dictionary order.

Added in version 3.1.

popitem(_last\=True_)[¶](https://docs.python.org/3/library/collections.html#collections.OrderedDict.popitem "Link to this definition")

The [`popitem()`](https://docs.python.org/3/library/collections.html#collections.OrderedDict.popitem "collections.OrderedDict.popitem") method for ordered dictionaries returns and removes a (key, value) pair. The pairs are returned in LIFO order if _last_ is true or FIFO order if false.

move\_to\_end(_key_, _last\=True_)[¶](https://docs.python.org/3/library/collections.html#collections.OrderedDict.move_to_end "Link to this definition")

Move an existing _key_ to either end of an ordered dictionary. The item is moved to the right end if _last_ is true (the default) or to the beginning if _last_ is false. Raises [`KeyError`](https://docs.python.org/3/library/collections.htmlexceptions.html#KeyError "KeyError") if the _key_ does not exist:

\>>>

```
<span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">d</span> <span class="o">=</span> <span class="n">OrderedDict</span><span class="o">.</span><span class="n">fromkeys</span><span class="p">(</span><span class="s1">'abcde'</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">move_to_end</span><span class="p">(</span><span class="s1">'b'</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="s1">''</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">d</span><span class="p">)</span>
<span class="go">'acdeb'</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">d</span><span class="o">.</span><span class="n">move_to_end</span><span class="p">(</span><span class="s1">'b'</span><span class="p">,</span> <span class="n">last</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="s1">''</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">d</span><span class="p">)</span>
<span class="go">'bacde'</span>
```

Added in version 3.2.

In addition to the usual mapping methods, ordered dictionaries also support reverse iteration using [`reversed()`](https://docs.python.org/3/library/collections.htmlfunctions.html#reversed "reversed").

Equality tests between [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") objects are order-sensitive and are roughly equivalent to `list(od1.items())==list(od2.items())`.

Equality tests between [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") objects and other [`Mapping`](https://docs.python.org/3/library/collections.htmlcollections.abc.html#collections.abc.Mapping "collections.abc.Mapping") objects are order-insensitive like regular dictionaries. This allows [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") objects to be substituted anywhere a regular dictionary is used.

Changed in version 3.5: The items, keys, and values [views](https://docs.python.org/3/library/collections.html../glossary.html#term-dictionary-view) of [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") now support reverse iteration using [`reversed()`](https://docs.python.org/3/library/collections.htmlfunctions.html#reversed "reversed").

Changed in version 3.6: With the acceptance of [**PEP 468**](https://peps.python.org/pep-0468/), order is retained for keyword arguments passed to the [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") constructor and its `update()` method.

Changed in version 3.9: Added merge (`|`) and update (`|=`) operators, specified in [**PEP 584**](https://peps.python.org/pep-0584/).

### [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") Examples and Recipes[¶](https://docs.python.org/3/library/collections.html#ordereddict-examples-and-recipes "Link to this heading")

It is straightforward to create an ordered dictionary variant that remembers the order the keys were _last_ inserted. If a new entry overwrites an existing entry, the original insertion position is changed and moved to the end:

```
<span></span><span class="k">class</span><span class="w"> </span><span class="nc">LastUpdatedOrderedDict</span><span class="p">(</span><span class="n">OrderedDict</span><span class="p">):</span>
    <span class="s1">'Store items in the order the keys were last added'</span>

    <span class="k">def</span><span class="w"> </span><span class="fm">__setitem__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">key</span><span class="p">,</span> <span class="n">value</span><span class="p">):</span>
        <span class="nb">super</span><span class="p">()</span><span class="o">.</span><span class="fm">__setitem__</span><span class="p">(</span><span class="n">key</span><span class="p">,</span> <span class="n">value</span><span class="p">)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">move_to_end</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
```

An [`OrderedDict`](https://docs.python.org/3/library/collections.html#collections.OrderedDict "collections.OrderedDict") would also be useful for implementing variants of [`functools.lru_cache()`](https://docs.python.org/3/library/collections.htmlfunctools.html#functools.lru_cache "functools.lru_cache"):

```
<span></span><span class="kn">from</span><span class="w"> </span><span class="nn">collections</span><span class="w"> </span><span class="kn">import</span> <span class="n">OrderedDict</span>
<span class="kn">from</span><span class="w"> </span><span class="nn">time</span><span class="w"> </span><span class="kn">import</span> <span class="n">time</span>

<span class="k">class</span><span class="w"> </span><span class="nc">TimeBoundedLRU</span><span class="p">:</span>
    <span class="s2">"LRU Cache that invalidates and refreshes old entries."</span>

    <span class="k">def</span><span class="w"> </span><span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">func</span><span class="p">,</span> <span class="n">maxsize</span><span class="o">=</span><span class="mi">128</span><span class="p">,</span> <span class="n">maxage</span><span class="o">=</span><span class="mi">30</span><span class="p">):</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">cache</span> <span class="o">=</span> <span class="n">OrderedDict</span><span class="p">()</span>      <span class="c1"># { args : (timestamp, result)}</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">func</span> <span class="o">=</span> <span class="n">func</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">maxsize</span> <span class="o">=</span> <span class="n">maxsize</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">maxage</span> <span class="o">=</span> <span class="n">maxage</span>

    <span class="k">def</span><span class="w"> </span><span class="fm">__call__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="o">*</span><span class="n">args</span><span class="p">):</span>
        <span class="k">if</span> <span class="n">args</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="p">:</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="o">.</span><span class="n">move_to_end</span><span class="p">(</span><span class="n">args</span><span class="p">)</span>
            <span class="n">timestamp</span><span class="p">,</span> <span class="n">result</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="p">[</span><span class="n">args</span><span class="p">]</span>
            <span class="k">if</span> <span class="n">time</span><span class="p">()</span> <span class="o">-</span> <span class="n">timestamp</span> <span class="o">&lt;=</span> <span class="bp">self</span><span class="o">.</span><span class="n">maxage</span><span class="p">:</span>
                <span class="k">return</span> <span class="n">result</span>
        <span class="n">result</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">func</span><span class="p">(</span><span class="o">*</span><span class="n">args</span><span class="p">)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="p">[</span><span class="n">args</span><span class="p">]</span> <span class="o">=</span> <span class="n">time</span><span class="p">(),</span> <span class="n">result</span>
        <span class="k">if</span> <span class="nb">len</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="p">)</span> <span class="o">&gt;</span> <span class="bp">self</span><span class="o">.</span><span class="n">maxsize</span><span class="p">:</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="o">.</span><span class="n">popitem</span><span class="p">(</span><span class="n">last</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
        <span class="k">return</span> <span class="n">result</span>
```

```
<span></span><span class="k">class</span><span class="w"> </span><span class="nc">MultiHitLRUCache</span><span class="p">:</span>
<span class="w">    </span><span class="sd">""" LRU cache that defers caching a result until</span>
<span class="sd">        it has been requested multiple times.</span>

<span class="sd">        To avoid flushing the LRU cache with one-time requests,</span>
<span class="sd">        we don't cache until a request has been made more than once.</span>

<span class="sd">    """</span>

    <span class="k">def</span><span class="w"> </span><span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">func</span><span class="p">,</span> <span class="n">maxsize</span><span class="o">=</span><span class="mi">128</span><span class="p">,</span> <span class="n">maxrequests</span><span class="o">=</span><span class="mi">4096</span><span class="p">,</span> <span class="n">cache_after</span><span class="o">=</span><span class="mi">1</span><span class="p">):</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">requests</span> <span class="o">=</span> <span class="n">OrderedDict</span><span class="p">()</span>   <span class="c1"># { uncached_key : request_count }</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">cache</span> <span class="o">=</span> <span class="n">OrderedDict</span><span class="p">()</span>      <span class="c1"># { cached_key : function_result }</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">func</span> <span class="o">=</span> <span class="n">func</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">maxrequests</span> <span class="o">=</span> <span class="n">maxrequests</span>  <span class="c1"># max number of uncached requests</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">maxsize</span> <span class="o">=</span> <span class="n">maxsize</span>          <span class="c1"># max number of stored return values</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">cache_after</span> <span class="o">=</span> <span class="n">cache_after</span>

    <span class="k">def</span><span class="w"> </span><span class="fm">__call__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="o">*</span><span class="n">args</span><span class="p">):</span>
        <span class="k">if</span> <span class="n">args</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="p">:</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="o">.</span><span class="n">move_to_end</span><span class="p">(</span><span class="n">args</span><span class="p">)</span>
            <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="p">[</span><span class="n">args</span><span class="p">]</span>
        <span class="n">result</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">func</span><span class="p">(</span><span class="o">*</span><span class="n">args</span><span class="p">)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">requests</span><span class="p">[</span><span class="n">args</span><span class="p">]</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">args</span><span class="p">,</span> <span class="mi">0</span><span class="p">)</span> <span class="o">+</span> <span class="mi">1</span>
        <span class="k">if</span> <span class="bp">self</span><span class="o">.</span><span class="n">requests</span><span class="p">[</span><span class="n">args</span><span class="p">]</span> <span class="o">&lt;=</span> <span class="bp">self</span><span class="o">.</span><span class="n">cache_after</span><span class="p">:</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">requests</span><span class="o">.</span><span class="n">move_to_end</span><span class="p">(</span><span class="n">args</span><span class="p">)</span>
            <span class="k">if</span> <span class="nb">len</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">requests</span><span class="p">)</span> <span class="o">&gt;</span> <span class="bp">self</span><span class="o">.</span><span class="n">maxrequests</span><span class="p">:</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">requests</span><span class="o">.</span><span class="n">popitem</span><span class="p">(</span><span class="n">last</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
        <span class="k">else</span><span class="p">:</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">requests</span><span class="o">.</span><span class="n">pop</span><span class="p">(</span><span class="n">args</span><span class="p">,</span> <span class="kc">None</span><span class="p">)</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="p">[</span><span class="n">args</span><span class="p">]</span> <span class="o">=</span> <span class="n">result</span>
            <span class="k">if</span> <span class="nb">len</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="p">)</span> <span class="o">&gt;</span> <span class="bp">self</span><span class="o">.</span><span class="n">maxsize</span><span class="p">:</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">cache</span><span class="o">.</span><span class="n">popitem</span><span class="p">(</span><span class="n">last</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
        <span class="k">return</span> <span class="n">result</span>
```

## [`UserDict`](https://docs.python.org/3/library/collections.html#collections.UserDict "collections.UserDict") objects[¶](https://docs.python.org/3/library/collections.html#userdict-objects "Link to this heading")

The class, [`UserDict`](https://docs.python.org/3/library/collections.html#collections.UserDict "collections.UserDict") acts as a wrapper around dictionary objects. The need for this class has been partially supplanted by the ability to subclass directly from [`dict`](https://docs.python.org/3/library/collections.htmlstdtypes.html#dict "dict"); however, this class can be easier to work with because the underlying dictionary is accessible as an attribute.

_class_ collections.UserDict(\[_initialdata_\])[¶](https://docs.python.org/3/library/collections.html#collections.UserDict "Link to this definition")

Class that simulates a dictionary. The instance’s contents are kept in a regular dictionary, which is accessible via the [`data`](https://docs.python.org/3/library/collections.html#collections.UserDict.data "collections.UserDict.data") attribute of [`UserDict`](https://docs.python.org/3/library/collections.html#collections.UserDict "collections.UserDict") instances. If _initialdata_ is provided, [`data`](https://docs.python.org/3/library/collections.html#collections.UserDict.data "collections.UserDict.data") is initialized with its contents; note that a reference to _initialdata_ will not be kept, allowing it to be used for other purposes.

In addition to supporting the methods and operations of mappings, [`UserDict`](https://docs.python.org/3/library/collections.html#collections.UserDict "collections.UserDict") instances provide the following attribute:

data[¶](https://docs.python.org/3/library/collections.html#collections.UserDict.data "Link to this definition")

A real dictionary used to store the contents of the [`UserDict`](https://docs.python.org/3/library/collections.html#collections.UserDict "collections.UserDict") class.

## [`UserList`](https://docs.python.org/3/library/collections.html#collections.UserList "collections.UserList") objects[¶](https://docs.python.org/3/library/collections.html#userlist-objects "Link to this heading")

This class acts as a wrapper around list objects. It is a useful base class for your own list-like classes which can inherit from them and override existing methods or add new ones. In this way, one can add new behaviors to lists.

The need for this class has been partially supplanted by the ability to subclass directly from [`list`](https://docs.python.org/3/library/collections.htmlstdtypes.html#list "list"); however, this class can be easier to work with because the underlying list is accessible as an attribute.

_class_ collections.UserList(\[_list_\])[¶](https://docs.python.org/3/library/collections.html#collections.UserList "Link to this definition")

Class that simulates a list. The instance’s contents are kept in a regular list, which is accessible via the [`data`](https://docs.python.org/3/library/collections.html#collections.UserList.data "collections.UserList.data") attribute of [`UserList`](https://docs.python.org/3/library/collections.html#collections.UserList "collections.UserList") instances. The instance’s contents are initially set to a copy of _list_, defaulting to the empty list `[]`. _list_ can be any iterable, for example a real Python list or a [`UserList`](https://docs.python.org/3/library/collections.html#collections.UserList "collections.UserList") object.

In addition to supporting the methods and operations of mutable sequences, [`UserList`](https://docs.python.org/3/library/collections.html#collections.UserList "collections.UserList") instances provide the following attribute:

data[¶](https://docs.python.org/3/library/collections.html#collections.UserList.data "Link to this definition")

A real [`list`](https://docs.python.org/3/library/collections.htmlstdtypes.html#list "list") object used to store the contents of the [`UserList`](https://docs.python.org/3/library/collections.html#collections.UserList "collections.UserList") class.

**Subclassing requirements:** Subclasses of [`UserList`](https://docs.python.org/3/library/collections.html#collections.UserList "collections.UserList") are expected to offer a constructor which can be called with either no arguments or one argument. List operations which return a new sequence attempt to create an instance of the actual implementation class. To do so, it assumes that the constructor can be called with a single parameter, which is a sequence object used as a data source.

If a derived class does not wish to comply with this requirement, all of the special methods supported by this class will need to be overridden; please consult the sources for information about the methods which need to be provided in that case.

## [`UserString`](https://docs.python.org/3/library/collections.html#collections.UserString "collections.UserString") objects[¶](https://docs.python.org/3/library/collections.html#userstring-objects "Link to this heading")

The class, [`UserString`](https://docs.python.org/3/library/collections.html#collections.UserString "collections.UserString") acts as a wrapper around string objects. The need for this class has been partially supplanted by the ability to subclass directly from [`str`](https://docs.python.org/3/library/collections.htmlstdtypes.html#str "str"); however, this class can be easier to work with because the underlying string is accessible as an attribute.

_class_ collections.UserString(_seq_)[¶](https://docs.python.org/3/library/collections.html#collections.UserString "Link to this definition")

Class that simulates a string object. The instance’s content is kept in a regular string object, which is accessible via the [`data`](https://docs.python.org/3/library/collections.html#collections.UserString.data "collections.UserString.data") attribute of [`UserString`](https://docs.python.org/3/library/collections.html#collections.UserString "collections.UserString") instances. The instance’s contents are initially set to a copy of _seq_. The _seq_ argument can be any object which can be converted into a string using the built-in [`str()`](https://docs.python.org/3/library/collections.htmlstdtypes.html#str "str") function.

In addition to supporting the methods and operations of strings, [`UserString`](https://docs.python.org/3/library/collections.html#collections.UserString "collections.UserString") instances provide the following attribute:

data[¶](https://docs.python.org/3/library/collections.html#collections.UserString.data "Link to this definition")

A real [`str`](https://docs.python.org/3/library/collections.htmlstdtypes.html#str "str") object used to store the contents of the [`UserString`](https://docs.python.org/3/library/collections.html#collections.UserString "collections.UserString") class.

Changed in version 3.5: New methods `__getnewargs__`, `__rmod__`, `casefold`, `format_map`, `isprintable`, and `maketrans`.
