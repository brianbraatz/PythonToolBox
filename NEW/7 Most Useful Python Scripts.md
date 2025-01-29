---
Description: 7 Most Useful Python Scripts - With Code Example
Notes: Discover 7 essential Python scripts to streamline your workflow, automate tasks, and enhance productivity. Simplify coding and achieve efficiency with these indispensable scripts
author: harendra21
Url: https://withcodeexample.com/7-most-useful-python-scripts/
Created: "2025-01-28  09:40:11"
Modified: 
Tags:
---

# 7 Most Useful Python Scripts - With Code Example

source: https://withcodeexample.com/7-most-useful-python-scripts/

> ## Excerpt
> Discover 7 essential Python scripts to streamline your workflow, automate tasks, and enhance productivity. Simplify coding and achieve efficiency with these indispensable scripts

---
# 7 Most Useful Python Scripts

[harendra21](https://withcodeexample.com/author/harendra21/)[Jan 10, 2025Aug 31, 2024](https://withcodeexample.com/7-most-useful-python-scripts/)

![](https://withcodeexample.com/wp-content/uploads/2025/01/7-most-useful-python-scripts-image.png)

7 Python scripts that were chosen for this post based on their overall usefulness, user-friendliness and favorable effects on your workload will be covered. They concentrate on text processing and file management and range in complexity from easy to intermediate. We’ll go over the following use cases in more detail:

## Image compression  

When creating assets for a new website or temporary landing page, you occasionally need to compress an image but may not want to do it yourself or may need to delegate the work to an outside image-processing provider. You may quickly and easily reduce the file size of JPG photographs while maintaining image quality by using the pillow package. Install `pillow` using `pip install pillow`.

The following example will shrink a 2.5 MB image to 293 KB:  
“\`py

# the pillow package can be imported as PIL  

from PIL import Image  
file\_path = “image\_uncompressed.jpg”  
img = Image.open(file\_path)  
height, width = img.size  
compressed = img.resize((height, width), Image.ANTIALIAS)  
compressed.save(“image\_compressed.jpg”, optimize=True,quality=9)  
“\`

## Wikipedia content  

Wikipedia offers excellent general summaries of numerous subjects. This data can be used to create training materials or reports, follow changes to a specific set of articles, or add more information to transactional emails. Thankfully, utilizing the Wikipedia library for Python makes it really simple to gather information.

Using `pip install wikipedia`, you may install the Wikipedia package. Once the installation is finished, you are prepared to start.

You can pull content directly from a certain page if you already know what it contains:  
“\`py  
import wikipedia  
page\_content = wikipedia.page(“parsec”).content

# outputs the text content of the “Parsec” page on wikipedia  

print(page\_content)

You can use this package to look for pages that contain a particular text match:

import wikipedia  
search\_results = wikipedia.search(“arc second”)

[![](https://res.cloudinary.com/harendra21/image/upload/w_600,f_auto/images/master-go-programming-language_yDv1gTCU.png)](https://bitli.in/kif9c5r)

# outputs an array of pages matching the search term  

print(search\_results)  
“\`

## Take text out of a PDF  

Using the PyPDF2 module, Python can also be used to quickly extract text from PDF files. For data mining, invoice reconciliation, or report preparation, extracting text from a PDF file is helpful. The extraction procedure can be automated with a few lines of code. To install the software, type `pip install PyPDF2` into your terminal. Here are a few illustrations of what you can accomplish using Py2PDF2:

Let’s say you only require the first page of a multipage PDF file that you received. With just a few lines of Python code, you can use the following script to extract text from the first page of a PDF:

“\`py

# Take text out of a PDF  

import PyPDF2  
pdfFileObj = open(‘example.pdf’, ‘rb’)  
pdfReader = PyPDF2.PdfFileReader(pdfFileObj)  
pageObj = pdfReader.getPage(0)  
texts = pageObj.extractText()  
print(texts)  
“\`

## Pandoc text processing  

A fully functional command-line utility that lets you convert markup between multiple formats is called Pandoc. This implies that you can use Pandoc to convert MediaWiki markup to DocBook or Markdown text directly to DCOX. Without limiting the data to a single format, markup-format conversion enables you to analyze external material or user-submitted data. With pip, the pandoc package may be installed. Here are a few instances of what pandoc can be used for.

Let’s imagine you receive a document in markdown format and you need to convert it to PDF. Pandoc simplifies this:  
“\`py  
import pandoc

in\_file = open(“example.md”, “r”).read()  
pandoc.write(in\_file, file=“example.pdf”, format=“pdf”)

Or perhaps you want to turn the markdown document into a JSON object. Use the script below to accomplish this:

import pandoc  
md\_string = “””

[![](https://res.cloudinary.com/harendra21/image/upload/w_600,f_auto/images/master-go-programming-language_yDv1gTCU.png)](https://bitli.in/kif9c5r)

# Hello from Markdown  

**This is a markdown string**  
“””  
input\_string = pandoc.read(md\_string)  
pandoc.write(input\_string, format=“json”, file=“md.json”)  
“\`

## Use Pydub to alter audio  

You may alter audio with Pydub, a Python program, including transcoding audio to different file formats like WAV or MP3. Additionally, Pydub has millisecond sample segmentation capabilities that may be particularly advantageous for machine learning workloads. By typing `pip install pydub` in your terminal, Pydub may be installed.

Let’s say you’re working with audio files and need to make sure the volume is correct for each file. This script can be used to automate the process:

`py   from pydub import AudioSegment`

`audio_file = AudioSegment.from_mp3("example.mp3")   louder_audio_file = audio_file + 18   louder_audio_file.export("example_louder.mp3", format="mp3")   `

## Text filter  

Python makes it easy to match and filter text using regular expressions, and the advantages can be significant. Consider a scenario in which you need to extract a credit card from the content of an email message and you have a system for batch processing sales-confirmation communications. You may quickly filter this data from any textual material using the script below, which can discover any credit card number that complies with the pattern:  
“\`py

# Filter Text  

# Import re module  

import re

# Take any string data  

string = “”“a string we are using to filter specific items.  
perhaps we would like to match credit card numbers  
mistakenly entered into the user input. 4444 3232 1010 8989  
and perhaps another? 9191 0232 9999 1111”“”

# Define the searching pattern  

pattern = ‘(([0-9](https://withcodeexample.com/7-most-useful-python-scripts//s+)?){4}){4}’

# match the pattern with input value  

found = re.search(pattern, string)  
print(found)

[![](https://res.cloudinary.com/harendra21/image/upload/w_600,f_auto/images/master-go-programming-language_yDv1gTCU.png)](https://bitli.in/kif9c5r)

# Print message based on the return value  

if found:  
print(“Found a credit card number!”)  
else:  
print(“No credit card numbers present in input”)  
“\`

## Find addresses  

Finding an address might be helpful for simple user-profiling tasks as well as shipping and delivery operations. Install geocoder by typing pip install geocoder into your terminal to get started. You may quickly determine the latitude and longitude of any address or identify an address from any set of coordinates by using the script below:

“\`py  
import geocoder  
address = “1600 Pennsylvania Ave NW, Washington DC USA”  
coordinates = geocoder.arcgis(address)  
geo = geocoder.arcgis(address)  
print(geo.latlng)
