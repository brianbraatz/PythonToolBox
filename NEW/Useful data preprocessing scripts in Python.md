---
Description: Useful data preprocessing scripts in Python | Better Programming
Notes: In this post, you can discover scripts concerning data processing to filter, aggregate, sort, and code performance optimization.
author: Kemal Toprak Uçar
Url: https://betterprogramming.pub/python-scripts-for-your-data-processing-operations-fa62503b31cf
Created: "2025-01-28  09:41:29"
Modified: 
Tags:
---

# Useful data preprocessing scripts in Python | Better Programming

source: https://betterprogramming.pub/python-scripts-for-your-data-processing-operations-fa62503b31cf

> ## Excerpt
> In this post, you can discover scripts concerning data processing to filter, aggregate, sort, and code performance optimization.

---
# 5 Python Scripts I Found Useful for Data Processing Operations

## Some practical scripts I discovered in my archives

[

![Kemal Toprak Uçar](https://miro.medium.com/v2/resize:fill:88:88/1*gj9jXupGvYb2KrcF0BMEvw.jpeg)





](https://medium.com/@ktoprakucar?source=post_page---byline--fa62503b31cf--------------------------------)

[

![Better Programming](https://miro.medium.com/v2/resize:fill:48:48/1*QNoA3XlXLHz22zQazc0syg.png)





](https://betterprogramming.pub/?source=post_page---byline--fa62503b31cf--------------------------------)

[Kemal Toprak Uçar](https://medium.com/@ktoprakucar?source=post_page---byline--fa62503b31cf--------------------------------)

·

Follow

Published in

[

Better Programming

](https://betterprogramming.pub/?source=post_page---byline--fa62503b31cf--------------------------------)

·

5 min read

·

Feb 1, 2023

128

Listen

Share

More

![](https://miro.medium.com/v2/resize:fit:875/1*dUzGnxbxKz3mKQsx8euMFA.jpeg)

Image by author: Long exposure of a moonrise ([source](https://www.flickr.com/photos/toprakucar/30772549447/))

I don’t know how it goes for you, but I need to reference my old projects for some scripts, even though I applied them at least 3–4 times a month for a while. From my point of view, my brain does not want me to memorize them and wants me to keep looking at my ancient tasks or Stack Overflow.

I confess I wanted to create a Jupyter notebook to construct a reference for my future applications. At the same time, I thought an article might be a helpful resource for someone, so you can discover scripts concerning data processing to filter, aggregate, sort, and code performance optimization in this article.

# Introduction

Conditions, loops, and exception handling are permanent terms, and they are language-independent. Various names can express them in different languages, but the contributions to the code logic are identical.

Adding more about the part of loops motivated me to write this article. In small-scale tasks, we ought not to care about code performance, but if users have this service as a library or a web service, response time or memory usage is crucial. Thus, using loops to generate new objects employing existing sequential data structures such as lists, arrays, or dictionaries may damage our code performance.

The scripts below may aid you in removing your loops, particularly data processing operations. As a real example, during my master’s research, I studied text classification, and the experiments required plenty of text preprocessing. In the first draft of the code, the feature extraction stage took around two days (yes, 40–42 hours). After I began to get benefits from the scripts below, the duration diminished to nearly two hours. In addition, to handling loops, they may help you increase readability by making them simple without over-engineering.

Before starting, I want to note I will also share a randomly-generated dataset, the script for the process, and the result for individual examples to maintain the context more perceptible.

# Groupby With Naming

Here we go! I want to start with the `group_by` method. If you work with data, there is no doubt you are spending a lot on the analysis. In SQL, Python, and R, `group_by` allocates a substantial portion of my code to accomplish aggregations for inferences. The issue I encounter is using a single column for numerous aggregations. So, the script below can allow you to deliver different names for various aggregations using a single column:

<iframe src="https://betterprogramming.pub/media/6cb1ab6e29d951d59de6d2f3ccc49d91" allowfullscreen="" frameborder="0" height="545" width="680" title="group_by_with_naming.ipynb" class="eo n fi ea bh" scrolling="no"></iframe>

# Filtering Nested Dictionaries

Since I have worked with PostgreSQL and JSON columns, dictionaries have become one of my best friends. Using loops to handle filtering is a popular approach in Python. After I realized I could filter nested dictionaries, the number of lines decreased to one line. In the code below, `dictonary_name.items()` returns key/value pairs inside the built-in filter method. At the lambda part, `[0]` represents the key, and `[1]` represents the value for each item. So, if we do `item[0][desired_column_name]` for a condition, we can easily filter the dictionary.

<iframe src="https://betterprogramming.pub/media/0f4dc4f825dc678bdf33844329bb746d" allowfullscreen="" frameborder="0" height="545" width="680" title="filter_nested_dictionary.ipynb" class="eo n fi ea bh" scrolling="no"></iframe>

# Sorting Nested Dictionaries

As I started to talk regarding dictionaries above, it sometimes is required to sort dictionaries without Pandas transformations. You can also manage sorting operations without employing loops as well. The built-in sorted method is used with a similar lambda utilization. If you desire to sort by nested value, you can employ `x[1][‘age’]`. To sort by keys, `x[0]` can work for you.

<iframe src="https://betterprogramming.pub/media/1631f903620227d84e20f669030817bd" allowfullscreen="" frameborder="0" height="545" width="680" title="sort_nested_dictonary.ipynb" class="eo n fi ea bh" scrolling="no"></iframe>

![](https://miro.medium.com/v2/resize:fit:875/1*P5ZeuCCGiMhYQYd7GwkkWQ.jpeg)

Photo by [Mimi Thian](https://unsplash.com/@mimithian?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/photos/ZKBzlifgkgw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

# Generate Rolling Features

Working with time-series data is one of my favorites. In addition to data analysis, I also enjoy feature engineering, which gives me additional motivation and satisfaction. For each group, we can generate moving features or compute the average of the earlier `N` values of the identical group. These feature generations can be produced by indices and values using a loop. It is possible to handle these feature generations by Pandas with a single line.

The `shift(n)` method allows us to obtain the previous values of the group. You can also determine which preceding value you want to pick with `n`. Furthermore, it’s possible to calculate the fundamental arithmetic operations of preceding elements, such as sum and average. At first, the `shift()` method excludes the present value, so you must use `expanding` to employ all the previous values. Ultimately, the desired value is generated by `mean()` or `sum()` methods.

In addition to the moving features, you can extract features based on previous n values. As cited above, we replace `expanding()` with `rolling()` to calculate the expected rolling value. You can provide a specific parameter to comprise how many preceding values are available for the computation. Afterward, `mean()` and `sum()` calculates the desired outcome.

<iframe src="https://betterprogramming.pub/media/95c0c9838151bed09f273d7b61aaaf46" allowfullscreen="" frameborder="0" height="545" width="680" title="generate_rolling_features.ipynb" class="eo n fi ea bh" scrolling="no"></iframe>

# Pandas Vectorization

We arrived at the final stop, Pandas vectorization. It makes up a large portion of the optimization story of my master’s study. In my honest opinion, utilizing loops is the most damaging approach in data preprocessing. In the early days of my Python voyage, I was digging the articles for significant code performance refinements. The experiments indicate that vectorization with pandas or numpy can enhance your performance, not including some specific cases.

In the following example, the commented method is the traditional practice that addresses the process item by item. Vectorization can involve the same logic. You can write a function that processes the values with a given column name. Afterward, the `apply` method can fulfill this function over the rows. To process row by row, you must pass `axis=1` to the `apply` method because the default axis value is `0`.

<iframe src="https://betterprogramming.pub/media/35c1f1d82f0f89fe244644c9dbb40edb" allowfullscreen="" frameborder="0" height="545" width="680" title="vectorize_with_pandas.ipynb" class="eo n fi ea bh" scrolling="no"></iframe>

![](https://miro.medium.com/v2/resize:fit:875/1*qjuZnAsQiGFIuE_-X-wGPQ.jpeg)

Photo by [Marvin Meyer](https://unsplash.com/fr/@marvelous?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/photos/SYTO3xs06fU?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

# Final Words

I wanted to share five useful Python scripts with examples. You can also find the examples in the [repository](https://github.com/ktoprakucar/data-manipulation-scripts.git). I hope my examples will be a good reference for your developments. I want to mention that I do not claim the examples above will boost your code performance. There might be some exceptional circumstances concerning memory.

If you have any feedback or recommendations for further advancement, please leave your ideas in the comments! :)
