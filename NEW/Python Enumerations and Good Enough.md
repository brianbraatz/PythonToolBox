---
Description: Python, Enumerations and “Good Enough” - Alyssa Coghlan's Python Notes
Notes: Note
author: 
Url: https://python-notes.curiousefficiency.org/en/latest/python3/enum_creation.html
Created: "2025-01-28  09:50:32"
Modified: 
Tags:
---

# Python, Enumerations and “Good Enough” - Alyssa Coghlan's Python Notes

source: https://python-notes.curiousefficiency.org/en/latest/python3/enum_creation.html

> ## Excerpt
> Note

---
# Python, Enumerations and “Good Enough”[¶](https://python-notes.curiousefficiency.org/en/latest/python3/enum_creation.html#python-enumerations-and-good-enough "Link to this heading")

Note

To provide feedback on this essay, use the [issue tracker](https://github.com/ncoghlan/misc/issues) or the DISQUS comments below.

Site last built: Jun 18, 2024 ([Change history](https://github.com/ncoghlan/misc/commits/master/notes/python3/enum_creation.rst))

[**PEP 435**](https://peps.python.org/pep-0435/) adds support for explicit enumerations in the Python standard library. One valid criticism of the accepted design is that there are some awkward compromises in the definition syntax, most notably the fact that you have to choose between explicit identification of the enum values in the class based syntax and the repetition of the class name and the use of strings in the functional declaration API. [Andrew Cooke’s review of the accepted PEP](http://www.acooke.org/cute/Pythonssad0.html) provides a good overview of that criticism.

## Why standardise enums at all?[¶](https://python-notes.curiousefficiency.org/en/latest/python3/enum_creation.html#why-standardise-enums-at-all "Link to this heading")

The idea of standardising enumerations has been kicking around for years. What finally tipped the balance this time? The major factor was a combination of Guido being sufficiently interested to rule on the many and varied debatable aspects of `Enum` runtime behaviour, and his declaration at the PyCon US 2013 language summit that we should just adopt Barry Warsaw’s `flufl.enum` package wholesale as a “good enough” solution and be done with it (as [**PEP 435**](https://peps.python.org/pep-0435/) describes, that didn’t end up happening, but having a concrete starting point like that helped focus the extensive subsequent design discussions).

The other motivating factor, however, was the ability to use enumerations to improve various error messages emitted by the standard library. One of the significant downsides of magic integers is the fact that they often result in cryptic error messages, unless the library authors take special care to translate numeric values back to their string equivalents when creating the error message. This limitation also applies to logging messages and value introspection when debugging. The additional name information in the representation of enumeration values provides that easier interpretation of otherwise generic values for free.

In almost all of the cases where we’re interested in this, however, the enumeration values are NOT arbitrary: instead, we’re exposing values defined in POSIX or IETF standards or by the underlying operating system, or ones where we’re exposing some internal implementation detail of the interpreter in a more robust and implementation independent way.

The other cases that we may update are ones that currently use `range` to generate the values, or else map variables to their own name as strings. For these cases, the [**PEP 435**](https://peps.python.org/pep-0435/) functional API is seen as being at least an improvement over the status quo, even though it remains somewhat inelegant.

## Requirements for the standard enum design[¶](https://python-notes.curiousefficiency.org/en/latest/python3/enum_creation.html#requirements-for-the-standard-enum-design "Link to this heading")

The core requirements for the standard enum design were based on a few standard library use cases:

-   exposing externally defined constants like those in [`errno`](https://docs.python.org/3/library/errno.html#module-errno "(in Python v3.12)") and [`socket`](https://docs.python.org/3/library/socket.html#module-socket "(in Python v3.12)")
    
-   exposing non-enum constants like those in `opcode` in a more user friendly way
    
-   exposing arbitrary constants like some of those in [`inspect`](https://docs.python.org/3/library/inspect.html#module-inspect "(in Python v3.12)")
    

The goal on the definition side was definitely “usable” rather than “beautiful” or “elegant”. Since a genuinely elegant declaration syntax was considered a “nice to have” rather than a “must have” for the design, it isn’t especially surprising that we failed to achieve it.

The declaration syntaxes in [**PEP 435**](https://peps.python.org/pep-0435/) are designed to support the first two use cases by letting us write ordinary Python code in the body of a class based enum declaration (including easy definition of aliases, since the externally defined constants we want to support often include aliases) and the shorthand functional API handles the “we don’t care about the values” use case well enough for us to consider it acceptable as the initial implementation.

## But _why_ isn’t elegance of declarations important?[¶](https://python-notes.curiousefficiency.org/en/latest/python3/enum_creation.html#but-why-isn-t-elegance-of-declarations-important "Link to this heading")

Elegance of declarations _is_ important, it just isn’t the only consideration. When designing additions to the Python standard library, we don’t consider “don’t worry, it’s magic” to be an acceptable explanation for how the new feature works (the zero-argument form of super() in Python 3 is a notable exception, and that violation of our usual principles has been the direct cause of a number of annoying issues due directly to its current conceptual incoherence relative to the rest of the language semantics).

The addition of enumerations represents only the second use of a custom metaclass in the standard library (the first was Abstract Base Classes), and we think it’s important that any deviations made from standard class behaviour are absolutely essential to the consistency of the runtime behaviour of enumerations (this includes items like having member definition order match iteration order, and being able to define integer-based enumerations that are transparently interoperable with the integers they replace).

In the case of the class-based declaration syntax, the long standing descriptor protocol means having class attributes behave differently when accessed through the class than they do when accessed in the class body is perfectly normal class behaviour. Thus, we’re comfortable with implicitly wrapping explicitly assigned names to turn them into enumeration members, and handling descriptors differently from other values.

However, having references to missing names implicitly create new enumeration members is _not_ something we’re comfortable with as part of a standard language feature. We did consider the idea (and, as noted in the PEP, it’s certainly feasible to implement enums that way), but it makes it impossible to write normal code in the class body (any typo would implicitly create a new enum member instead of reporting a `NameError` as expected).

Why would anyone want to write normal code in the body of an enumeration? One reason is because that’s the way you create enumerations with custom behaviour: by defining methods in their class definition, just as you do for other classes. If references to missing names implicitly created a new enumeration member, then making a typo in a default value in a method definition would behave very strangely.

More importantly, we plan to [tighten up the formal specification](http://bugs.python.org/issue17960) for [`locals()`](https://docs.python.org/3/library/functions.html#locals "(in Python v3.12)") so that it can be manipulated in the class body to define enumerations programmatically. For several of the standard library use cases (where the enum represents an externally defined mapping of names to values) this is far more important than the ability to concisely define enumerations where we don’t care about the values (which is largely covered by the functional API anyway).

The pedagogical aspect of requiring explicit assignments is that allowing implicit creation of enumeration values elevates the “don’t worry it’s magic” factor well beyond what we consider necessary. With the current design, the code in the body reads like normal Python code, the same as any other class. With implicit creation, enumerations behave wildly differently from anything else in Python. Yes, it _can_ be done, but that doesn’t mean it _should_ (at least, not as the standard incarnation of the syntax).

The question of whether or not to allow aliasing by default was a close-run thing, eventually decided by Guido opting for easier support for POSIX and IETF standards (which often include aliases) over easier detection of typos when entering values directly. While I briefly thought we could use a little more magic to support aliasing without supporting independently binding two different names to the same value, that turned out to be [more problematic than I expected](http://bugs.python.org/issue17959) so we’re sticking with Guido’s original decision.

However, it may still be possible [add a simple class decorator](http://bugs.python.org/issue18042) that makes it easy to ensure there a no accidental aliases when they are not desired.

## Support for alternate declaration syntaxes[¶](https://python-notes.curiousefficiency.org/en/latest/python3/enum_creation.html#support-for-alternate-declaration-syntaxes "Link to this heading")

That said, something we’re deliberately aiming to do with the [**PEP 435**](https://peps.python.org/pep-0435/) enum implementation is to make the `enum.EnumMeta` _metaclass_ amenable to customisation. Metaclasses are ultimately just classes (albeit ones with a specific use case in Python’s data model), so you can subclass and tweak them in order to change their behaviour, as long as they were designed with that kind of tweaking in mind. In the case of enums, we plan to rely on that to let people create their own variations on enum _declaration_ syntax, while largely retaining the runtime semantics of the standard enumerations.

Personally, I expect to see variants that enable the following behaviours:

-   Autonumbered enums with a sentinel value (such as Ellipsis). This is used as an `enum.EnumMeta` [subclassing test case](https://bitbucket.org/stoneleaf/ref435/src/7e775db6c25d730fc03f579fdac68066317608e3/test_ref435.py?at=default#cl-481) in the test suite for the reference implementation and allows code like:
    
    ```
    <span></span><span class="k">class</span> <span class="nc">Color</span><span class="p">(</span><span class="n">AutoNumberedEnum</span><span class="p">):</span>
        <span class="n">red</span> <span class="o">=</span> <span class="o">...</span>
        <span class="n">green</span> <span class="o">=</span> <span class="o">...</span>
        <span class="n">blue</span> <span class="o">=</span> <span class="o">...</span>
    ```
    
    A relatively straightforward variant of this would use the “= …” notation to mean “use the enum member’s qualified name as its value”.
    
-   Implicit enums that _don’t_ really support normal code execution in the class body, and allow the above to be simplified further. It’s another variant of the autonumbered example in the test suite, but one that diverges substantially from normal Python semantics: merely _mentioning_ a name will create a new reference to that name. While there are a number of ways to get into trouble when doing this, the basic concept would be to modify `__prepare__` on the metaclass to return a namespace that implements `__missing__` as returning a custom sentinel value and overrides \_\_getitem\_\_ to treat repeating a name as an error:
    
    ```
    <span></span><span class="k">class</span> <span class="nc">Color</span><span class="p">(</span><span class="n">ImplicitEnum</span><span class="p">):</span>
        <span class="n">red</span>
        <span class="n">green</span>
        <span class="n">blue</span>
        <span class="n">green</span> <span class="c1"># This should trigger an exception</span>
    ```
    
    When the metaclass is putting the class together, it then looks at all the entries set to the sentinel value and then either numbers them in order (if using integers as values) or else sets each of them to the qualified name of the member (if using strings as values)
    
-   Extensible enums, that make it easier to include elements of another enum inside a larger one. One feature of `flufl.enum` that was lost in the journey to the standard library is the ability to inherit enum members from a parent enum, as a consequence of making it so that standard enum members are actually instances of the corresponding enum.
    
    This change makes it easy to add new behaviour to enums - you just define methods in the enum definition. However, the combination of inheriting members _and_ adding additional behaviour is incoherent - you can’t do both and get a sensible result, as you either don’t actually inherit the members (as you want to add additional behaviour, and thus wrap them in a different type) _or_ you use the inherited members, which then don’t support the additional added behaviours.
    
    The other problem with enum extension-through-inheritance is that one of the standard expectations of class inheritance is that the base class be usable wherever an instance of the parent class is expected. However, one of the assumptions of enumerations is that `isinstance(x, MyEnum)` implies `x in MyEnum` and vice-versa, and that’s automatically violated as soon as you add members in a subclass (the members of the subclass will satisfy the first condition, but not the second).
    
    PEP 435 addressed this by adding the restriction that you simply can’t subclasse an enumeration that already has defined members (this is a similar restriction to the one that Java places on their enumerations).
    
    I suspect that extensible enums are going to require a slightly different abstraction, closer to the `flufl.enum` model, where the group members are aggregated from multiple independent underlying enumerations. For example, something like:
    
    ```
    <span></span><span class="k">class</span> <span class="nc">MoreColors</span><span class="p">(</span><span class="n">AggregateEnum</span><span class="p">,</span> <span class="n">extends</span><span class="o">=</span><span class="n">Color</span><span class="p">):</span>
        <span class="n">cyan</span> <span class="o">=</span> <span class="o">...</span>
        <span class="n">magenta</span> <span class="o">=</span> <span class="o">...</span>
    ```
    

To some degree, this “customise the metaclass if you want something different” approach _is_ indeed a copout - we’re providing a lowest-common-demoninator enum implementation, and leaving it to people to add their own syntactic sugar on top if they really want to. On the other hand, this is an approach the Python core development team has been using successfully for a _long_ time: providing a basic initial implementation, and then seeing how that initial approach is used in the real world before tweaking it in future versions.

## Improving the functional APIs[¶](https://python-notes.curiousefficiency.org/en/latest/python3/enum_creation.html#improving-the-functional-apis "Link to this heading")

We’re _not_ happy with the current state of the functional APIs for either named tuples and enumerations. However, rather than being limited to either of those specific use cases, the limitations of those APIs are symptomatic of a deeper language design problem relating to the creation of arbitrary objects that know their own names and their locations in the import namespace, along with the inability to cleanly specify lists of identifiers in a way that is visible to and checked by the compiler.

Thus, any improvements to these APIs will likely be based on addressing those broader design problems. It doesn’t make sense to hold up standardisation of enumerations for the resolution of those much harder design problems though, particularly when the immediately available workarounds aren’t _that_ ugly.

This is also the reason we’re not going to provide an `ImplicitEnum` implementation in the standard library at this time - it’s not yet clear if that’s the right answer to the problem.

I did like the idea of using the members qualified names as their values for the enum functional API, though, so I [filed an issue](http://bugs.python.org/issue17947) suggesting we change to that after the core implementation of the PEP has been put in place. However, as I noted when ultimately rejecting that change, the current approach works well with any likely concrete subclasses (specifically numbers and strings), whereas the same cannot be said for using the member names (that would break as soon as you tried to use the functional API with a numeric subclass).
