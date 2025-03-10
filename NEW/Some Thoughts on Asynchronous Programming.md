---
Description: Some Thoughts on Asynchronous Programming - Alyssa Coghlan's Python Notes
Notes: Some of the feedback I sent to Guido regarding PEP 3156 didn’t make the
cut for inclusion in the PEP itself. I still consider it useful background
and explanatory info, but that PEP’s already going to be massive, so it
makes sense that he’d prefer to keep the PEP text aimed at those that
already understand the specific problems he is trying to solve.
author: 
Url: https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html
Created: "2025-01-28  09:50:58"
Modified: 
Tags:
---

# Some Thoughts on Asynchronous Programming - Alyssa Coghlan's Python Notes

source: https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html

> ## Excerpt
> Some of the feedback I sent to Guido regarding PEP 3156 didn’t make the
cut for inclusion in the PEP itself. I still consider it useful background
and explanatory info, but that PEP’s already going to be massive, so it
makes sense that he’d prefer to keep the PEP text aimed at those that
already understand the specific problems he is trying to solve.

---
# Some Thoughts on Asynchronous Programming[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#some-thoughts-on-asynchronous-programming "Link to this heading")

Some of the feedback I sent to Guido regarding [**PEP 3156**](https://peps.python.org/pep-3156/) didn’t make the cut for inclusion in the PEP itself. I still consider it useful background and explanatory info, but that PEP’s already going to be massive, so it makes sense that he’d prefer to keep the PEP text aimed at those that already understand the specific problems he is trying to solve.

As with all essays on these pages, feedback is welcome via the [issue tracker](https://github.com/ncoghlan/misc/issues) or [Twitter](https://twitter.com/ncoghlan_dev). If you want to comment on [**PEP 3156**](https://peps.python.org/pep-3156/) itself, use the [python-ideas mailing list](http://mail.python.org/mailman/listinfo/python-ideas).

## A Bit of Background Info[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#a-bit-of-background-info "Link to this heading")

The term “Asynchronous I/O” is used to refer to two distinct, but related, concepts. The first of these concepts is an execution model for network programming, where the scalability of an I/O bound application is governed by the number of open socket connections that can be handled in a single OS process rather than by the number of concurrent OS level threads. This approach can significantly improve the scalability of an application, as most POSIX based operating systems can effectively manage thousands or tens of thousands of open socket connections without any significant tuning of process options, but only hundreds of threads (with the default size of the C stack being a key culprit - consuming the resources of an entire thread to wait for an I/O operation can waste a whole lot of memory). Disk I/O can also be scaled in this manner, but it’s substantially less common to do so (since disk latency is typically orders of magnitude better than network latency).

The second of these concepts is a programming model based on explicit cooperative multi-threading where yield points are visible locally (rather than the pre-emptive multi-threading provided by OS level threads or implicit cooperative multi-threading where any function call or magic method invocation may hide a suspension point). One key goal of this explicit programming model is to change the nature of the bugs typically seen in an application. Rather than (potentially subtle) correctness bugs due to incorrect manipulation of data structures shared between preemptively scheduled threads, or inadvertently yielding control when a data structure is in a partially modified state, applications and libraries using this explicit programming model see performance bugs where an erroneous call to a synchronous API blocks the entire application. (Note that pre-emptively multi-threaded applications can still see the later kind of bug if a blocking call is made while holding a lock on a critical data structure). Another perceived benefit is that this model better matches the reality of event based programming: every event is dealt with immediately, and either translated into a response (whether that’s a network message or a UI update) based on information already available locally or else into waiting for a different event (via some kind of callback API).

The key problem with this explicitly asynchronous programming model, of course, is that if an operation starts as synchronous, converting it to asynchronous requires modifying every point that calls it to yield control appropriately when necessary.

The Stackless Python project, and the greenlets library it inspired, aim to provide the first benefit, while retaining the standard synchronous programming model for application level code. This is a hugely powerful technique, as it allows the scalability benefits to be gained without needing to rewrite the entire application stack. Object-Relational-Mappers, for example, usually assume that it is OK to query or write to a database as a side effect of attribute retrieval or modification. Greenlets can often be used to implicitly turn such attribute access operations into asynchronous I/O operations, by replacing the underlying database access APIs (if the lowest layer is written in Python rather than C, it may even be possible to do so via monkey-patching), while switching to explicit asynchronous programming would require rewriting the entire ORM. Using explicit asynchronous programming also prevents entirely much of the syntactic sugar provided by ORMs, such as implicitly loading of data from the database when retrieving an attribute from an object.

[**PEP 3156**](https://peps.python.org/pep-3156/), however, like the Twisted networking engine and the Tornado web server, is aimed at providing _both_ benefits: an explicitly asynchronous programming model based on cooperative multi-threading where the suspension points are clearly marked in the individual functions and scalability is limited by the number of concurrent I/O operations supported per process rather than the number of OS level threads.

I think this quote from Guido in PEP 343 (the PEP that added the `with` statement) is also relevant to the asynchronous IO PEP:

> But the final blow came when I read Raymond Chen’s rant about [flow-control macros](http://blogs.msdn.com/oldnewthing/archive/2005/01/06/347666.aspx). Raymond argues convincingly that hiding flow control in macros makes your code inscrutable, and I find that his argument applies to Python as well as to C.

When writing implicitly asynchronous code, you have to assume that you may lose control of the execution at any point, since even something as innocous as retrieving an attribute from an object may suspend the thread of control. By contrast, with explicitly asynchronous code, it is safe to assume that you have sole access to shared data structures between suspension points.

While the inherent duplication between the synchronous programming model and the asynchronous programming model is unlikely to ever be eliminated, the aim of [**PEP 3156**](https://peps.python.org/pep-3156/) is to help reduce the unnecessary duplication between the asynchronous programming frameworks, as well as to provide improved asynchronous programming capabilities as part of the standard library, with an easier migration path to third party projects like Twisted and Tornado. This improved asynchronous infrastructure should also benefit greenlets-based synchronous-to-asynchronous adapters, as there should be a richer asynchronous ecosystem to draw from when implementing the networking side of frameworks like `gevent` (more on that below).

Furthermore, Guido’s PEP aims to take full advantage of the improved support added to the language for using generators as coroutines in PEP 342 and PEP 380, as well as aligning with the API for the OS level parallel execution techniques supported by the `concurrent.futures` standard library module added in PEP 3148. I’ve occasionally spoken of the changes to Python’s generators over the years as a way to make writing Twisted code less painful, and see the new PEP as a natural continuation of that effort.

## Gevent and PEP 3156[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#gevent-and-pep-3156 "Link to this heading")

If you look at gevent’s [monkey patching code](https://github.com/SiteSupport/gevent/blob/master/gevent/monkey.py), you can see that one of the key features it provides is the ability to act as a “synchronous to asynchronous adapter”: taking code that assumes a synchronous blocking model and running it based on asynchronous IO instead.

From an application point of view, that’s an amazing capability, and it allows some things that are impossible in an explicitly asynchronous model (such as implicitly suspending inside a magic method, which is needed for features like lazy loading of attributes from the database in an ORM).

Where even a framework like `gevent` can benefit from the transport and protocol infrastructure that will be exposed by [**PEP 3156**](https://peps.python.org/pep-3156/) is that, as with other projects like Twisted and Tornado, it will become easier to avoid reinventing the wheel on the _asynchronous I/O_ side of things.

There will thus be 3 models for integrating asynchronous and synchronous code:

-   Thread pools: [**PEP 3156**](https://peps.python.org/pep-3156/) will allow operations to be passed to separate threads, allowing blocking operations to be executed without suspending the main thread. This will allow explicitly asynchronous code to take advantage of existing blocking operations without blocking the main loop.
    
-   Blocking: one of the capabilities anticipated in [**PEP 3156**](https://peps.python.org/pep-3156/) is the ability to effectively block on an asynchronous operation, running the event loop until the operation completes. This won’t give any scalability benefits, but should allow synchronous applications to take advantage of at least some asynchronous transport and protocol implementations without needing to rewrite them as synchronous operations.
    
-   Implicit asynchronous operations: `gevent` will be able to share elements of the IO stack with other asynchronous frameworks, while still allowing gevent\` users to write apparently synchronous code.
    

## Using Special Methods in Explicitly Asynchronous Code[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#using-special-methods-in-explicitly-asynchronous-code "Link to this heading")

One challenge that arises when writing explicitly asynchronous code is how to compose it with other elements of Python syntax like operators, for loops and with statements. The key to doing this effectively is the same as that adopted when designing the [`concurrent.futures.as_completed()`](https://docs.python.org/3/library/concurrent.futures.html#concurrent.futures.as_completed "(in Python v3.12)") iterator API: these other operations should always return a Future or coroutine object, even if the result of the operation happens to be available immediately. This allows the user code to consistently retrieve the result via `yield from`. The implementation of `__iter__` on Future objects and coroutines is such that they will return immediately if the result is already available, avoiding the overhead of a trip through the event loop.

### Naming conventions[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#naming-conventions "Link to this heading")

The examples below follow Guido’s convention in NDB, where it is assumed that synchronous and asynchronous versions of operations are offered in the same namespace. The synchronous blocking versions are considered the “normal” API, and the asynchronous variants are marked with the `_async` suffix.

If an API is entirely asynchronous (as in [**PEP 3156**](https://peps.python.org/pep-3156/) itself) then the suffix may be dispensed with - users should assume that all operations are asynchronous. In such an API, marking any synchronous operations API with a `_sync` suffix may be desirable, but I don’t know of any real world usage of that convention.

### Asynchronous conditional expressions[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#asynchronous-conditional-expressions "Link to this heading")

While loops and if statements are a very simple case, as it’s merely a matter of using an asynchronous expression in place of the normal boolean query:

```
<span></span><span class="k">while</span> <span class="p">(</span><span class="k">yield from</span> <span class="n">check_async</span><span class="p">()):</span>
    <span class="c1"># check_async() always returns a Future or coroutine</span>
    <span class="c1"># The loop will suspend if necessary when evaluating the condition</span>
```

### Asynchronous Iterators[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#asynchronous-iterators "Link to this heading")

Asynchronous iterators work by producing Futures or coroutines at each step. These are then waited for explicitly in the body of the loop:

```
<span></span><span class="k">for</span> <span class="n">f</span> <span class="ow">in</span> <span class="n">iterator_async</span><span class="p">():</span>
    <span class="c1"># Each iteration step always returns a Future or coroutine immediately</span>
    <span class="c1"># Retrieving the result is then flagged as a possible suspension point</span>
    <span class="n">x</span> <span class="o">=</span> <span class="k">yield from</span> <span class="n">f</span>
```

For example, this approach is useful when executing multiple operations in parallel, and you want to process the individual results as they become available:

```
<span></span><span class="k">for</span> <span class="n">f</span> <span class="ow">in</span> <span class="n">as_completed</span><span class="p">(</span><span class="n">operations</span><span class="p">):</span>
    <span class="n">result</span> <span class="o">=</span> <span class="k">yield from</span> <span class="n">f</span>
    <span class="c1"># Process the result</span>
```

This is very similar to the way the existing concurrent.futures module operates, with the `f.result()` call replaced by the explicit suspension point `yield from f`.

### Asynchronous Context Managers[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#asynchronous-context-managers "Link to this heading")

Asynchronous context managers are able to cope with blocking operations on entry to a with statement by implementing them as a Future or coroutine that produces a context manager as its result. The \_\_enter\_\_ and \_\_exit\_\_ methods on this context manager must themselves be non-blocking:

```
<span></span><span class="k">with</span> <span class="p">(</span><span class="k">yield from</span> <span class="n">cm_async</span><span class="p">)</span> <span class="k">as</span> <span class="n">x</span><span class="p">:</span>
    <span class="c1"># The potentially blocking operation happens in cm_async.__iter__</span>
    <span class="c1"># The __enter__ and __exit__ methods on the result cannot</span>
    <span class="c1"># suspend execution</span>
```

Alternatively, a Future or coroutine may be returned from \_\_enter\_\_, similar to the usage of asynchronous iterators:

```
<span></span><span class="k">with</span> <span class="n">cm_async</span> <span class="k">as</span> <span class="n">f</span><span class="p">:</span>
    <span class="c1"># The potentially blocking operation happens in f.__iter__</span>
    <span class="n">x</span> <span class="o">=</span> <span class="k">yield from</span> <span class="n">f</span>
    <span class="c1"># The __exit__ method on the CM still cannot suspend execution</span>
```

For example, either of these models may be used to implement an “asynchronous lock” that is used to control shared access to a data structure even across operations which require handing control back to the event loop.

However, it is not currently possible to handle operations (such as database transactions) that may need to suspend execution in the \_\_exit\_\_ method. In such cases, it is necessary to either adopt a synchronous-to-asynchronous adapter framework (such as gevent) or else revert to the explicit try statement form:

```
<span></span><span class="n">x</span> <span class="o">=</span> <span class="n">yield_from</span> <span class="n">cm</span><span class="o">.</span><span class="n">enter_async</span><span class="p">()</span>
<span class="k">try</span><span class="p">:</span>
    <span class="o">...</span>
<span class="k">except</span> <span class="ne">Exception</span> <span class="k">as</span> <span class="n">ex</span><span class="p">:</span>
    <span class="n">cm</span><span class="o">.</span><span class="n">handle_error_async</span><span class="p">(</span><span class="n">ex</span><span class="p">)</span>
<span class="k">else</span><span class="p">:</span>
    <span class="n">cm</span><span class="o">.</span><span class="n">handle_success_async</span><span class="p">()</span>
```

### Asynchronous Operators[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#asynchronous-operators "Link to this heading")

The approach described above generalises to other operators, such as addition or attribute access: rather than returning a result directly, an API may be defined as returning a Future or coroutine, to be turned into a concrete result with `yield from`:

```
<span></span><span class="n">add_async</span> <span class="o">=</span> <span class="n">objA</span> <span class="o">+</span> <span class="n">objB</span>
<span class="n">add_result</span> <span class="o">=</span> <span class="k">yield from</span> <span class="n">add_async</span>
```

In practice, it is likely to be clearer to use separate methods for potentially asynchronous operations, making it obvious through naming conventions (such as the `_async` suffix) that the operations return a Future or coroutine rather than producing the result directly. Synchronous-to-asynchronous adapters also have a role to play here in allowing code that relies heavily on operator overloading to interact cleanly with asynchronous libraries.

### Additional Asynchronous Syntax[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/async_programming.html#additional-asynchronous-syntax "Link to this heading")

The `yield` and `yield from` keywords apply directly to the subsequent expression. As noted above, this means they can’t easily be used to affect the operation of magic methods invoked implicitly as part of other syntax. Accordingly, that you means you can’t have an asynchronous context manager that needs to suspend in `__exit__`, nor can you easily write an asynchronous comprehension.

However, a new keyword should allow certain subexpressions in `for` loops, `with` statements and comprehensions to be flagged for invocation as `yield from expr` rather than using the result of the expression directly.

Using `yielding` as the example keyword, usage would look like the following:

```
<span></span><span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">yielding</span> <span class="n">async_iterable</span><span class="p">:</span>
    <span class="c1"># Current generator may be suspended each time __next__ is called.</span>
    <span class="c1"># Semantics are exactly the same as the workaround noted above:</span>
    <span class="c1"># the __next__ is expected to return a Future or coroutine, which</span>
    <span class="c1"># the interpreter will then invoke with "yield from". The difference</span>
    <span class="c1"># is that in this case the invocation is implied by the "yielding"</span>
    <span class="c1"># keyword, avoid the need to spell out the temporary varibale</span>

<span class="c1"># Similarly, in the following comprehensions, the current generator</span>
<span class="c1"># may be suspended as each value is retrieved from the iterable</span>
<span class="n">x</span> <span class="o">=</span> <span class="p">[</span><span class="n">x</span> <span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">yielding</span> <span class="n">async_iterable</span><span class="p">]</span>
<span class="n">y</span> <span class="o">=</span> <span class="p">{</span><span class="n">x</span> <span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">yielding</span> <span class="n">async_iterable</span><span class="p">}</span>
<span class="n">z</span> <span class="o">=</span> <span class="p">{</span><span class="n">k</span><span class="p">:</span><span class="n">v</span> <span class="k">for</span> <span class="n">k</span><span class="p">,</span> <span class="n">v</span> <span class="ow">in</span> <span class="n">yielding</span> <span class="n">async_iterable</span><span class="p">}</span>

<span class="k">with</span> <span class="n">yielding</span> <span class="n">async_cm</span> <span class="k">as</span> <span class="n">x</span><span class="p">:</span>
    <span class="c1"># Current generator may be suspended when __enter__ and __exit__</span>
    <span class="c1"># are called. As with _iter__, for __enter__, the semantics are the</span>
    <span class="c1"># same as in the workaround noted above, except that the temporary</span>
    <span class="c1"># variable is hidden in the interpreter.</span>
    <span class="c1"># Unlike the workaround, the dedicated syntax means __exit__ is</span>
    <span class="c1"># also invoked asynchronously, so it can be used to implement</span>
    <span class="c1"># asynchronous database transactions.</span>
```
