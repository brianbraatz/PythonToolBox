---
Description: 7 Python Scripts for Machine Learning | Python in Plain English
Notes: Image Object Detection, Working with Pandas, Sentiment Analysis, Graph Plotting, Fetch Datasets, AI Image Generator, and Text Analysing.
author: Haider Imtiaz
Url: https://python.plainenglish.io/7-python-scripts-for-machine-learning-756e31be8b76
Created: "2025-01-28  09:44:58"
Modified: 
Tags:
---

# 7 Python Scripts for Machine Learning | Python in Plain English

source: https://python.plainenglish.io/7-python-scripts-for-machine-learning-756e31be8b76

> ## Excerpt
> Image Object Detection, Working with Pandas, Sentiment Analysis, Graph Plotting, Fetch Datasets, AI Image Generator, and Text Analysing.

---
# 7 Python Scripts for Machine Learning

## _Collection of Killer Python Scripts for Machine learning Projects_

[

![Haider Imtiaz](https://miro.medium.com/v2/resize:fill:88:88/1*F3MJ00WKjZzX4-OcZBwPSw.jpeg)





](https://codedev101.medium.com/?source=post_page---byline--756e31be8b76--------------------------------)

[

![Python in Plain English](https://miro.medium.com/v2/resize:fill:48:48/1*VA3oGfprJgj5fRsTjXp6fA@2x.png)





](https://python.plainenglish.io/?source=post_page---byline--756e31be8b76--------------------------------)

[Haider Imtiaz](https://codedev101.medium.com/?source=post_page---byline--756e31be8b76--------------------------------)

·

Follow

Published in

[

Python in Plain English

](https://python.plainenglish.io/?source=post_page---byline--756e31be8b76--------------------------------)

·

7 min read

·

Oct 30, 2022

35

Listen

Share

More

![](https://miro.medium.com/v2/resize:fit:875/1*gm0KeDVUemDi_m-mGPhUiA.jpeg)

**Designed by** [**wayhomestudio**](https://www.freepik.com/wayhomestudio) **on** [**Freepik**](https://www.freepik.com/)

Tired of writing and searching codes for your **machine learning** projects then why not use some **pre-made** python scripts like Pandas scripts, Text analyzing code, object detection code, and many more? In this article, I will show you **7 Python Scripts for Machine learning Projects.** So mark it in your list and let's get started.

> You can have data without information but you cannot have information without data
> 
> — Daniel Keys Moron

# 👉Image Object Detection

Now no need to write long code for detecting different objects in your Images. This script uses the Transformers module that will let you detect objects in your images with few lines of code.

It’s a handy script for detecting simple and complex objects in multiple images.

```
<span id="5b8b" class="qc ox gd py b ig qd qe l iu qf" data-selectable-paragraph=""># Object Detection<br># pip install Pillow<br># pip install transformers<br># pip install timm</span><span id="365f" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">from PIL import Image<br>from transformers import pipeline</span><span id="06ef" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">def Detect_Objects(img):<br>    detector = pipeline("object-detection")<br>    img = Image.open(img)<br>    results = detector(img)<br>    for result in results:<br>        print(result["label"], result["score"])</span><span id="d04d" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">Detect_Objects("test.jpg")</span>
```

# 👉Working with Pandas

If you need help reading your dataset or performing some data analysis, then here is the python script that will be a handy tool for you. It's a handy cheat sheet for programs.

```
<span id="0c5a" class="qc ox gd py b ig qd qe l iu qf" data-selectable-paragraph=""># Pandas<br># pip install pandas</span><span id="3210" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">import pandas as p</span><span id="7438" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Read datasets<br>data = p.read_csv('data.csv')</span><span id="79da" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Count missing values<br>print(data.isnull().sum())</span><span id="e908" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Get Total Size of dataset<br>print(data.shape)</span><span id="e2bb" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Drop NaN values<br>data = data.dropna()</span><span id="487c" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Fill NaN values<br>data = data.fillna(0)</span><span id="5c7e" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Convert to list<br>data = data.values.tolist()</span><span id="8865" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Convert Columns to list<br>data = data['column name'].values.tolist()</span><span id="ee94" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Convert Rows to list<br>data = data.loc['row name'].values.tolist()</span><span id="613b" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Count Duplicate<br>data = data.duplicated().sum()</span><span id="2c0b" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Drop Duplicate<br>data = data.drop_duplicates()</span><span id="bd33" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Drop Column<br>data = data.drop('column name', axis=1)</span><span id="c4bc" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Select row in range<br>data = data.loc[0:10]</span><span id="36b1" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Get Unique Values info<br>print(data.nunique())</span><span id="5f67" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Insert new data<br>data.insert(0, 'column name', 'value')</span><span id="f30b" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># save to csv<br>data.to_csv('data.csv', index=False)</span>
```

# 👉Sentiment Analysis

Analyze any text you want with this awesome Python script that uses the Transformer module. This script is handy when you don’t need to write a long code sentiment analysis.

```
<span id="04a1" class="qc ox gd py b ig qd qe l iu qf" data-selectable-paragraph=""># Sentiment analysis<br># pip install transformers</span><span id="309c" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">from transformers import pipeline as pl</span><span id="0260" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">def sentiment_analysis(text):<br>    analyser = pl("sentiment-analysis")<br>    report = analyser(text)[0]<br>    print("Sentiment: ", report['label'])<br>    print("Score: ", report['score'])</span><span id="d99a" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">sentiment_analysis("I love to eat pizza")</span>
```

# 👉Graph Plotting

Need to plot graphs and charts to visualize your data or results then this Python script is for you. This script uses the Matplotlib module that let you plot lines, bars, scatter, and many other graphs and charts.

```
<span id="0144" class="qc ox gd py b ig qd qe l iu qf" data-selectable-paragraph=""># Graph Plotting<br># pip install matplotlib</span><span id="e43f" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">import matplotlib.pyplot as plot</span><span id="d1d1" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Plot Line Graph<br>x = [1, 2, 3, 4, 5]<br>y = [1, 4, 9, 16, 25]<br>plot.plot(x, y)<br>plot.show()</span><span id="3bca" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Plot Bar Graph<br>x = [1, 2, 3, 4, 5]<br>y = [1, 4, 9, 16, 25]<br>plot.bar(x, y)</span><span id="2ee2" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Plot Multi line Graph<br>x = [1, 2, 3, 4, 5]<br>y = [1, 4, 9, 16, 25]<br>plot.plot(x, y)<br>x = [1, 2, 3, 4, 5]<br>y = [1, 8, 27, 64, 125]<br>plot.plot(x, y)<br>plot.show()</span><span id="496e" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Plot Scatter Graph<br>x = [1, 2, 3, 4, 5]<br>y = [1, 4, 9, 16, 25]<br>plot.scatter(x, y)</span><span id="9943" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Plot Histogram Graph<br>x = [1, 2, 3, 4, 5]<br>y = [1, 4, 9, 16, 25]<br>plot.hist(x, y)</span><span id="6559" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Plot Pie Graph<br>x = [1, 2, 3, 4, 5]<br>y = [1, 4, 9, 16, 25]<br>plot.pie(x, y)<br>plot.show()</span><span id="cd50" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Hexbin graph<br>x = [1, 2, 3, 4, 5]<br>y = [1, 4, 9, 16, 25]<br>plot.hexbin(x, y)<br>plot.show()</span><span id="d417" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Label The graph <br>x = [1, 2, 3, 4, 5]<br>y = [1, 4, 9, 16, 25]<br>plot.plot(x, y)<br>plot.xlabel('x - axis')<br>plot.ylabel('y - axis')<br>plot.title('My first graph!')<br>plot.show()</span>
```

# 👉Fetch Datasets

We always need datasets to train our Machine learning algorithm or AI. This script will show you how you can fetch any datasets from the **hugging face** website directly in your Python code.

```
<span id="7836" class="qc ox gd py b ig qd qe l iu qf" data-selectable-paragraph=""># Fetch Datasets<br># pip install datasets</span><span id="f1ae" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">import datasets as ds</span><span id="1c20" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Fetch All Datasets<br>data = ds.list_datasets()<br>print(data)</span><span id="50cd" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Fetch Dataset<br>data = ds.load_dataset('amazon_us_reviews')<br>print(data)</span><span id="ac7f" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Fetch Train and Test Dataset<br>data = ds.load_dataset('amazon_us_reviews', split=['train', 'test'])<br>print(data)</span><span id="779b" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Save dataset in csv format<br>data = ds.load_dataset('amazon_us_reviews', split='train')<br>data.to_csv('amazon_us_reviews.csv', index=False)</span><span id="4c8e" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Save dataset in json format<br>data = ds.load_dataset('amazon_us_reviews', split='train')<br>data.to_json('amazon_us_reviews.json', orient='records')</span><span id="8bf6" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Fetch Train and Test Dataset<br>data = datasets.load_dataset('amazon_us_reviews', split=['train', 'test'])<br>print(data)</span><span id="8fdd" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Save dataset in json format<br>data = datasets.load_dataset('amazon_us_reviews', split='train')<br>data.to_json('amazon_us_reviews.json', orient='records')</span>
```

# 👉AI Image Generator

Generate Images based on your inputted text. This script use api request to generate an image based on your text and then download the image with the requests module.

```
<span id="0ac5" class="qc ox gd py b ig qd qe l iu qf" data-selectable-paragraph=""># AI Image Generator<br># pip install requests</span><span id="0934" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">import requests</span><span id="2454" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">text = "World in 2050"</span><span id="6db7" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">headers = {'api-key': 'quickstart-QUdJIGlzIGNvbWluZy4uLi4K'}<br>data = {'text': text}<br>r = requests.post('<a class="af nh" href="https://api.deepai.org/api/text2img'" rel="noopener ugc nofollow" target="_blank">https://api.deepai.org/api/text2img'</a>, headers=headers, data=data)</span><span id="a49a" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># download the image<br>url = r.json()['output_url']<br>r = requests.get(url, allow_redirects=True)<br>f = open('image.jpg', 'wb')<br>f.write(r.content)</span>
```

# 👉Text Analysing

Need help in analyzing text with **NLTK** then here is your savior script that had common functions of **NLTK** you will need to build an awesome Text analyzing program.

```
<span id="5f22" class="qc ox gd py b ig qd qe l iu qf" data-selectable-paragraph=""># Text Analysing<br># pip install nltk</span><span id="83ae" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">import nltk<br>from nltk.tokenize import word_tokenize<br>from nltk.corpus import stopwords<br>from nltk.stem import *</span><span id="2319" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph="">text = "I am learning Python. I am learning Data Science and Machine Learning"</span><span id="cd79" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Tokenize<br>tokens = word_tokenize(text)<br>print(tokens)</span><span id="5133" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Remove Stopwords<br>stop_words = set(stopwords.words('english'))<br>filtered_tokens = [w for w in tokens if not w in stop_words]<br>print(filtered_tokens)</span><span id="a2a0" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Stemming<br>stemmer = PorterStemmer()<br>stemmed_tokens = [stemmer.stem(w) for w in filtered_tokens]<br>print(stemmed_tokens)</span><span id="0bdd" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Lemmatization<br>lemmatizer = WordNetLemmatizer()<br>lemmatized_tokens = [lemmatizer.lemmatize(w) for w in filtered_tokens]<br>print(lemmatized_tokens)</span><span id="b6d4" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># POS Tagging<br>pos_tagged_tokens = nltk.pos_tag(tokens)<br>print(pos_tagged_tokens)</span><span id="7034" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Named Entity Recognition<br>named_entities = nltk.ne_chunk(pos_tagged_tokens)<br>print(named_entities)</span><span id="f34d" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Chunking<br>grammar = "NP: {&lt;DT&gt;?&lt;JJ&gt;*&lt;NN&gt;}"<br>cp = nltk.RegexpParser(grammar)<br>result = cp.parse(pos_tagged_tokens)<br>print(result)</span><span id="f38c" class="qc ox gd py b ig qg qe l iu qf" data-selectable-paragraph=""># Parsing<br>grammar = "NP: {&lt;DT&gt;?&lt;JJ&gt;*&lt;NN&gt;}"<br>cp = nltk.RegexpParser(grammar)<br>result = cp.parse(pos_tagged_tokens)<br>print(result)</span>
```

# 👉 Final thoughts
