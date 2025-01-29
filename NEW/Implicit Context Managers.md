---
Description: Implicit Context Managers - Alyssa Coghlan's Python Notes
Notes: View this page
author: 
Url: https://python-notes.curiousefficiency.org/en/latest/pep_ideas/implicit_with.html
Created: "2025-01-28  09:51:34"
Modified: 
Tags:
---

# Implicit Context Managers - Alyssa Coghlan's Python Notes

source: https://python-notes.curiousefficiency.org/en/latest/pep_ideas/implicit_with.html

> ## Excerpt
> View this page

---
# Implicit Context Managers[¶](https://python-notes.curiousefficiency.org/en/latest/pep_ideas/implicit_with.html#implicit-context-managers "Link to this heading")

Boredom & Laziness: [http://www.boredomandlaziness.org/2011/01/some-goals-for-python-33.html](http://www.boredomandlaziness.org/2011/01/some-goals-for-python-33.html)

Basic concept is to add an optional `__cm__` method that relates to context managers the way `__iter__` relates to iterators.

I still don’t have a pithy name like “iterable” for “objects with an implicit context manager”, but the passage of time has at least cemented “context manager” as referring specifically to objects with `__enter__` and `__exit__` methods.
