---
Description: Python Collections: Essentials to Advanced - StrataScratch
Notes: Mastering Python Collections: In-depth exploration of Lists, Dictionaries, Tuples, and advanced data structures for optimal coding efficiency
author: Written by:Nathan RosidiAuthor Bio
Url: https://www.stratascratch.com/blog/python-collections-essentials-to-advanced/
Created: "2025-01-28  09:43:02"
Modified: 
Tags:
---

# Python Collections: Essentials to Advanced - StrataScratch

source: https://www.stratascratch.com/blog/python-collections-essentials-to-advanced/

> ## Excerpt
> Mastering Python Collections: In-depth exploration of Lists, Dictionaries, Tuples, and advanced data structures for optimal coding efficiency

---
# Python Collections: Essentials to Advanced

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='800'%20width='1200'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Python Collections Guide](https://cdn.sanity.io/images/oaglaatp/production/e398d2c160e82416cd745e20d4be9bf85e6c0fd3-1200x800.png?w=1200&h=800&auto=format)

![Python Collections Guide](https://cdn.sanity.io/images/oaglaatp/production/e398d2c160e82416cd745e20d4be9bf85e6c0fd3-1200x800.png?w=1200&h=800&auto=format)

##### Categories

[Python](https://www.stratascratch.com/blog/categories/python/)[Guides](https://www.stratascratch.com/blog/categories/guides/)

___

-   ![Author Avatar](https://cdn.sanity.io/images/oaglaatp/production/64162bd8e019c9dfa4c3a691a677c3348454e8de-398x398.png?w=100&h=100&fit=crop)
    
    Written by:  
    Nathan Rosidi
    
    Author Bio

___

_Mastering Python Collections: In-depth exploration of Lists, Dictionaries, Tuples, and advanced data structures for optimal coding efficiency_

In programming, picking the right way to store data is very important. It makes solving hard problems easier. Python is great for this, simple and well-designed. Python Collections are a big part of this.

Python collections make handling data easy and smart, which means your code works well and quickly.

In this article, we will talk about the Python Collections module. We will look into its parts and learn why they are important. We will also see how to use them in real situations. From lists and tuples to ChainMaps and special data structures, we want to give you a full understanding.

# Beginner Collections in Python

Let's focus on beginner Python collections: lists, dictionaries, and tuples.

[Python Lists](https://www.stratascratch.com/blog/a-comprehensive-guide-to-python-lists-and-their-power/) allow you to store items in a sequence. You can add or take away items, making them flexible and easy for beginners. Here is it’s syntax.

```
<span style="color: rgb(0, 134, 179);">list</span><span> = [</span><span style="color: rgb(33, 145, 97);">"here"</span><span>, </span><span style="color: rgb(33, 145, 97);">"is"</span><span>, </span><span style="color: rgb(33, 145, 97);">"a"</span><span>, </span><span style="color: rgb(33, 145, 97);">"simple"</span><span>,</span><span style="color: rgb(33, 145, 97);">"list"</span><span>]
</span><span></span><span style="color: rgb(0, 134, 179);">list</span><span>
</span>
```

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='56.00000000000001'%20width='656'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Beginner Collections in Python](https://cdn.sanity.io/images/oaglaatp/production/dce59e7d310c42fdf287b9ac25d1806209b06e02-656x56.png?w=656&h=56&auto=format)

![Beginner Collections in Python](https://cdn.sanity.io/images/oaglaatp/production/dce59e7d310c42fdf287b9ac25d1806209b06e02-656x56.png?w=656&h=56&auto=format)

[Python Dictionaries](https://www.stratascratch.com/blog/python-dictionaries-master-key-value-data-structures/), on the other hand, are about matching keys to values. It is as a way to store information where you can quickly find something by its name. This makes them perfect for organizing and retrieving data, especially when you know exactly what you're looking for.

```
<span style="color: rgb(0, 134, 179);">dict</span><span> = {</span><span style="color: rgb(33, 145, 97);">"here"</span><span>: </span><span style="color: rgb(33, 145, 97);">"is"</span><span>, </span><span style="color: rgb(33, 145, 97);">"a"</span><span>: </span><span style="color: rgb(33, 145, 97);">"simple"</span><span>,</span><span style="color: rgb(33, 145, 97);">"list"</span><span> : </span><span style="color: rgb(33, 145, 97);">"."</span><span>}
</span><span></span><span style="color: rgb(0, 134, 179);">print</span><span>(</span><span style="color: rgb(0, 134, 179);">dict</span><span>.keys())
</span><span></span><span style="color: rgb(0, 134, 179);">print</span><span>(</span><span style="color: rgb(0, 134, 179);">dict</span><span>.values())
</span>
```

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='146'%20width='1224'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Beginner Collections in Python](https://cdn.sanity.io/images/oaglaatp/production/01be7efb34c5508bd4d5d79ba928b7c87736668d-1224x146.png?w=1224&h=146&auto=format)

![Beginner Collections in Python](https://cdn.sanity.io/images/oaglaatp/production/01be7efb34c5508bd4d5d79ba928b7c87736668d-1224x146.png?w=1224&h=146&auto=format)

Tuples, on the other hand, are used to store items, but you can't change them once they're made. This is useful for data that should stay the same, providing a simple and reliable way to handle constant information.

```
<span>my_tuple = (</span><span style="color: rgb(33, 145, 97);">"here"</span><span>, </span><span style="color: rgb(33, 145, 97);">"is"</span><span>, </span><span style="color: rgb(33, 145, 97);">"a"</span><span>, </span><span style="color: rgb(33, 145, 97);">"simple"</span><span>, </span><span style="color: rgb(33, 145, 97);">"tuple"</span><span>)
</span>my_tuple

```

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='100'%20width='1224'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Beginner Collections in Python](https://cdn.sanity.io/images/oaglaatp/production/36eb7cf92d1ddf3cf532023621fe872b4019baaf-1224x100.png?w=1224&h=100&auto=format)

![Beginner Collections in Python](https://cdn.sanity.io/images/oaglaatp/production/36eb7cf92d1ddf3cf532023621fe872b4019baaf-1224x100.png?w=1224&h=100&auto=format)

Together, these collections form the foundation of data handling in Python, offering different ways for beginners to manage and use data effectively. Now let’s look at advanced collections.

# Advanced Collections in Python

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='621'%20width='1200'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Advanced Collections in Python](https://cdn.sanity.io/images/oaglaatp/production/e7e068a241a4bf21202271ae039841c5ffe8ba14-1200x621.png?w=1200&h=621&auto=format)

![Advanced Collections in Python](https://cdn.sanity.io/images/oaglaatp/production/e7e068a241a4bf21202271ae039841c5ffe8ba14-1200x621.png?w=1200&h=621&auto=format)

The Counter, for example. It's a special kind of dictionary for counting things that can be counted, like words in a text or items in a list. It shows how Python can easily solve common problems.

Then, there's the OrderedDict. Before Python 3.7, dictionaries did not save the order of items. OrderedDict solved this, so developers can rely on the order of items for their work.

Another important one is the defaultdict. It gives a default value to keys that are not there, which is very useful for complex data and stops errors with keys.

These advanced collections show Python's commitment to providing strong and flexible ways to store data, making programming a lot easier.

## Practical Applications of Advanced Python Collections

The following practical applications showcase how Python Collections can be used to solve real-world problems in a Pythonic, efficient manner, making them an indispensable part of any Python developer's toolkit.

Python Collections come to life when applied to real-world problems. Let's look at some practical examples with code to illustrate their usage.

#### 1\. Managing User Sessions with defaultdict:

Take, for instance, a web application that needs to manage user sessions. A defaultdict can be used to handle session data, automatically creating a new session for users who don't have one yet. This simplifies the logic required to check and create sessions, making the code cleaner and more efficient.

```
<span style="color: rgb(149, 65, 33);">from</span><span> collections </span><span style="color: rgb(149, 65, 33);">import</span><span> defaultdict
</span>
<span># Initialize a defaultdict </span><span style="color: rgb(149, 65, 33);">with</span><span> an empty </span><span style="color: rgb(149, 65, 33);">dictionary</span><span> </span><span style="color: rgb(149, 65, 33);">as</span><span> the </span><span style="color: rgb(149, 65, 33);">default</span><span> </span><span style="color: rgb(149, 65, 33);">value</span><span>
</span>user_sessions = defaultdict(dict)

<span># Simulate </span><span style="color: rgb(149, 65, 33);">user</span><span> sessions
</span><span>user_sessions[</span><span style="color: rgb(33, 145, 97);">'Alice'</span><span>][</span><span style="color: rgb(33, 145, 97);">'last_login'</span><span>] = </span><span style="color: rgb(33, 145, 97);">'2023-01-01'</span><span>
</span><span>user_sessions[</span><span style="color: rgb(33, 145, 97);">'Bob'</span><span>][</span><span style="color: rgb(33, 145, 97);">'last_login'</span><span>] = </span><span style="color: rgb(33, 145, 97);">'2023-01-02'</span><span>
</span>
<span># Accessing a </span><span style="color: rgb(0, 134, 179);">new</span><span> </span><span style="color: rgb(149, 65, 33);">user</span><span style="color: rgb(33, 145, 97);">'s session creates it automatically
</span><span style="color: rgb(33, 145, 97);">print(user_sessions['</span><span>Ev</span><span style="color: rgb(33, 145, 97);">e'])
</span><span style="color: rgb(33, 145, 97);">
</span><span style="color: rgb(33, 145, 97);"></span>
```

Here is the output.

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='64'%20width='1224'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Application of Python Collection to manage user sessions with defaultdict](https://cdn.sanity.io/images/oaglaatp/production/2361401ec5d0c26625289813e7736f4fa389b17e-1224x64.png?w=1224&h=64&auto=format)

![Application of Python Collection to manage user sessions with defaultdict](https://cdn.sanity.io/images/oaglaatp/production/2361401ec5d0c26625289813e7736f4fa389b17e-1224x64.png?w=1224&h=64&auto=format)

This code above automatically handles the creation of a session for new users, avoiding the need for manual checks or session initialization.

#### 2\. Data Analysis with Counter

In data analysis, a Counter is invaluable.

Analyzing datasets often involves counting occurrences of various elements. With a Counter, this task becomes a matter of a few lines of code, allowing you to focus more on the analysis part rather than the counting mechanics.

Let’s see how the Counter class makes this process straightforward.

```
<span style="color: rgb(149, 65, 33);">from</span><span> collections </span><span style="color: rgb(149, 65, 33);">import</span><span> Counter
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Sample data: words in a sentence</span><span>
</span><span>words = [</span><span style="color: rgb(33, 145, 97);">'apple'</span><span>, </span><span style="color: rgb(33, 145, 97);">'banana'</span><span>, </span><span style="color: rgb(33, 145, 97);">'apple'</span><span>, </span><span style="color: rgb(33, 145, 97);">'orange'</span><span>, </span><span style="color: rgb(33, 145, 97);">'banana'</span><span>, </span><span style="color: rgb(33, 145, 97);">'apple'</span><span>]
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Count the occurrences of each word</span><span>
</span>word_count = Counter(words)

<span></span><span style="color: rgb(0, 134, 179);">print</span><span>(word_count)
</span>
```

Here is the output.

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='74'%20width='1242'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Application of Python Collection to analyze data with counter](https://cdn.sanity.io/images/oaglaatp/production/842dc9d447e57400320f50116e3a3f99d5b1902c-1242x74.png?w=1242&h=74&auto=format)

![Application of Python Collection to analyze data with counter](https://cdn.sanity.io/images/oaglaatp/production/842dc9d447e57400320f50116e3a3f99d5b1902c-1242x74.png?w=1242&h=74&auto=format)

This simple example demonstrates how Counter can be used to tally up items, a frequent requirement in data analysis.

#### 3\. Configuration Management with ChainMap:

And when dealing with configurations or settings, a ChainMap can be a game-changer. It allows you to create a single view of multiple dictionaries, like default settings and user-specific settings. This way, you can easily manage and override configurations without the need for complex merging logic. Let’s see how ChainMap is useful to deal with multiple layers of settings.

```
<span style="color: rgb(149, 65, 33);">from</span><span> collections </span><span style="color: rgb(149, 65, 33);">import</span><span> ChainMap
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Default settings</span><span>
</span><span>default_settings = {</span><span style="color: rgb(33, 145, 97);">'theme'</span><span>: </span><span style="color: rgb(33, 145, 97);">'light'</span><span>, </span><span style="color: rgb(33, 145, 97);">'notifications'</span><span>: </span><span style="color: rgb(149, 65, 33);">True</span><span>}
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># User-specific settings</span><span>
</span><span>user_settings = {</span><span style="color: rgb(33, 145, 97);">'theme'</span><span>: </span><span style="color: rgb(33, 145, 97);">'dark'</span><span>}
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Combine settings with ChainMap</span><span>
</span>combined_settings = ChainMap(user_settings, default_settings)

<span></span><span style="color: rgb(0, 134, 179);">print</span><span>(combined_settings[</span><span style="color: rgb(33, 145, 97);">'theme'</span><span>])  
</span><span></span><span style="color: rgb(0, 134, 179);">print</span><span>(combined_settings[</span><span style="color: rgb(33, 145, 97);">'notifications'</span><span>])  
</span>
```

Here is the output.

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='82'%20width='806'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Application of Python Collection to configure management with Chainmap](https://cdn.sanity.io/images/oaglaatp/production/53509626575bdb7f8560d237b75489166ffc31a6-806x82.png?w=806&h=82&auto=format)

![Application of Python Collection to configure management with Chainmap](https://cdn.sanity.io/images/oaglaatp/production/53509626575bdb7f8560d237b75489166ffc31a6-806x82.png?w=806&h=82&auto=format)

This code elegantly handles the combination of two dictionaries, prioritizing the user settings over the defaults.

#### 4\. Efficient Queue Operations with Deque

Deque stands for "double-ended queue" and is a collection that supports adding and removing items from either end efficiently. This makes it perfect for tasks that require a queue structure, such as processing tasks in order or managing states in games.

```
<span style="color: rgb(149, 65, 33);">from</span><span> collections </span><span style="color: rgb(149, 65, 33);">import</span><span> deque
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Initialize a deque</span><span>
</span><span>tasks = deque([</span><span style="color: rgb(33, 145, 97);">'task1'</span><span>, </span><span style="color: rgb(33, 145, 97);">'task2'</span><span>, </span><span style="color: rgb(33, 145, 97);">'task3'</span><span>])
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Enqueue tasks to the front and back</span><span>
</span><span>tasks.append(</span><span style="color: rgb(33, 145, 97);">'task4'</span><span>)  </span><span style="color: rgb(64, 128, 128); font-style: italic;"># add to the end</span><span>
</span><span>tasks.appendleft(</span><span style="color: rgb(33, 145, 97);">'task0'</span><span>)  </span><span style="color: rgb(64, 128, 128); font-style: italic;"># add to the front</span><span>
</span>
<span></span><span style="color: rgb(0, 134, 179);">print</span><span>(tasks)  
</span>
```

Here is the output.

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='56'%20width='938'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Application of Python Collection for efficient queue operations with deque](https://cdn.sanity.io/images/oaglaatp/production/71423da59f9e2b80f2016d753cd2fb033b7b3a4a-938x56.png?w=938&h=56&auto=format)

![Application of Python Collection for efficient queue operations with deque](https://cdn.sanity.io/images/oaglaatp/production/71423da59f9e2b80f2016d753cd2fb033b7b3a4a-938x56.png?w=938&h=56&auto=format)

#### 5\. Structured Data with NamedTuple

Namedtuple provides a way to create tuple-like objects that have fields accessible by attribute lookup as well as being indexable and iterable. This brings clear advantages in terms of code readability and structure.

```
<span style="color: rgb(149, 65, 33);">from</span><span> collections </span><span style="color: rgb(149, 65, 33);">import</span><span> namedtuple
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Create a namedtuple to represent a point in 2D space</span><span>
</span><span>Point = namedtuple(</span><span style="color: rgb(33, 145, 97);">'Point'</span><span>, [</span><span style="color: rgb(33, 145, 97);">'x'</span><span>, </span><span style="color: rgb(33, 145, 97);">'y'</span><span>])
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Instantiate a Point object</span><span>
</span><span>p = Point(</span><span style="color: rgb(64, 160, 112);">10</span><span>, y=</span><span style="color: rgb(64, 160, 112);">20</span><span>)
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Accessing the elements</span><span>
</span><span></span><span style="color: rgb(0, 134, 179);">print</span><span>(p.x, p.y) 
</span>
```

Here is the output.

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='52'%20width='924'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Application of Python Collection for structured data with named tuple](https://cdn.sanity.io/images/oaglaatp/production/80bbc36de44e09f70d7581668268d365f9a4282d-924x52.png?w=924&h=52&auto=format)

![Application of Python Collection for structured data with named tuple](https://cdn.sanity.io/images/oaglaatp/production/80bbc36de44e09f70d7581668268d365f9a4282d-924x52.png?w=924&h=52&auto=format)

#### 6\. Maintaining Order with OrderedDict

OrderedDict is a special type of dictionary that remembers the order in which its contents are added. Even though regular dictionaries now maintain insertion order as of Python 3.7,

OrderedDict can still be useful when you need to ensure the order is maintained, such as when you're exporting data to a CSV file where the column order matters.

```
<span style="color: rgb(149, 65, 33);">from</span><span> collections </span><span style="color: rgb(149, 65, 33);">import</span><span> OrderedDict
</span>
<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Create an OrderedDict to remember the order items are added</span><span>
</span>favorite_fruits = OrderedDict()

<span></span><span style="color: rgb(64, 128, 128); font-style: italic;"># Add items to the OrderedDict</span><span>
</span><span>favorite_fruits[</span><span style="color: rgb(33, 145, 97);">'apple'</span><span>] = </span><span style="color: rgb(33, 145, 97);">'green'</span><span>
</span><span>favorite_fruits[</span><span style="color: rgb(33, 145, 97);">'banana'</span><span>] = </span><span style="color: rgb(33, 145, 97);">'yellow'</span><span>
</span><span>favorite_fruits[</span><span style="color: rgb(33, 145, 97);">'cherry'</span><span>] = </span><span style="color: rgb(33, 145, 97);">'red'</span><span>
</span>
<span></span><span style="color: rgb(0, 134, 179);">print</span><span>(favorite_fruits) 
</span>
```

Here is the output.

![](data:image/svg+xml;charset=utf-8,%3Csvg%20height='50'%20width='1226'%20xmlns='http://www.w3.org/2000/svg'%20version='1.1'%3E%3C/svg%3E)

![Application of Python Collection for maintaining order with ordereddict](https://cdn.sanity.io/images/oaglaatp/production/89ab0593ab3486781521a4eb695e9c5c4065cf1c-1226x50.png?w=1226&h=50&auto=format)

![Application of Python Collection for maintaining order with ordereddict](https://cdn.sanity.io/images/oaglaatp/production/89ab0593ab3486781521a4eb695e9c5c4065cf1c-1226x50.png?w=1226&h=50&auto=format)

## Best Practices and Tips for Using Python Collections

In this article, we explored various Python collections like lists, dictionaries, tuples, and more advanced structures such as ChainMaps, Counters, and defaultdicts. Now, let's see on some best practices and tips we learned along the way.

**Choosing the Right Collection**: We saw how different collections serve different purposes. Picking the right one, like using lists for ordered items or dictionaries for key-value pairs, is crucial for efficient programming.

**Efficiency Matters**: Throughout our examples, efficiency was key. Remember to use collections in a way that keeps your code running fast. For example, using sets for fast membership testing.

**Mutable vs Immutable**: We discussed mutable collections like lists and immutable ones like tuples. Choosing between them depends on whether your data should change or stay the same.

**Nested Collections**: We also saw collections within collections, like dictionaries inside lists.This can be complex, but it's powerful for organizing data.

**Error Handling**: Common mistakes with collections, such as key errors in dictionaries, were highlighted. Learning to handle these errors gracefully is important.

**Functional Programming with Collections**: We didn't cover this in depth, but using collections with functional programming concepts like map and filter can make your code more elegant.

**Comprehensions for Simplicity**: Finally, using comprehensions to create collections can make your code more readable and concise.

## Conclusion

We have learned about Python Collections. They come in many types and uses, and they make Python programming look good. We saw simple ones like lists, tuples, and dictionaries, and more complex ones like ChainMaps, Counters, defaultdicts, and more.

Keep practicing if you're a data scientist, developer, or Python fan.Here, you can see [top 30 python interview questions and answers](https://www.stratascratch.com/blog/top-30-python-interview-questions-and-answers/). The more you use the concepts you have learned, the easier they get.

On StrataScratch platform, there is a bunch of interview questions from big companies, including Fortune 500 and FAANG, which will make your path easier to pass through.

## FAQ’s

#### What are Python collections?

Python collections are ways to store and organize data. They help you keep your data in order and make it easy to work with. Examples include lists, dictionaries, and tuples.

#### How many collections are there in Python?

Python has several collections. The main ones are lists, dictionaries, tuples, sets, and a few special ones from the collections module like Counter, defaultdict, and OrderedDict.

#### What is the Python equivalent of Java collections?

In Python, collections like lists, dictionaries, and sets are similar to Java's ArrayList, HashMap, and HashSet. Python's collections module also has more advanced types, similar to some in Java's collections framework.

#### What are the collections elements in Python?

Collection elements in Python are the items or data stored in a collection. For example, in a list, each item is an element. In a dictionary, each key-value pair is an element.
