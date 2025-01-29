---
Description: Python automation: 9 scripts to automate critical workflows
Notes: Programming can save you time and simplify your life. Try out these Python automation scripts to make your day less tedious.
author: Luke Strauss
Url: https://zapier.com/blog/python-automation/
Created: "2025-01-28  09:41:57"
Modified: 
Tags:
---

# Python automation: 9 scripts to automate critical workflows

source: https://zapier.com/blog/python-automation/

> ## Excerpt
> Programming can save you time and simplify your life. Try out these Python automation scripts to make your day less tedious.

---
# Python automation: 9 scripts to automate critical workflows

By Luke Strauss · December 10, 2024

[](https://facebook.com/ZapierApp/)[](https://twitter.com/zapier)[](https://linkedin.com/company/zapier)

![Hero image with the Python logo](https://images.ctfassets.net/lzny33ho1g45/O97hZQ1aOEmlyKFuO2IuD/55f05f194e124c28674e713730124e7b/Python.jpg?w=1520&fm=jpg&q=31&fit=thumb&h=760)

I don't know about you, but the highlight of _my_ day is completing mind-numbing and repetitive tasks—manual data entry, downloading hundreds of images one-by-one, and searching every file on my desktop for the right document. 

5 things you should automate today

[Start automating](https://zapier.com/blog/what-you-should-automate/)

Can't relate? Weird. But lucky for you, we live in a time where computers can help with the busywork we've become so accustomed to doing by hand. Python is a particular favorite programming language among those new to task automation.

I consulted with a Python expert to develop nine Python automation scripts, each of which can automate tasks you've been doing manually for way too long.

**Table of contents:**

-   [Why automate tasks with Python?](https://zapier.com/blog/python-automation//#why-python)
    
-   [How to run a Python script](https://zapier.com/blog/python-automation//#how-to-python)
    
-   [9 Python automation script examples](https://zapier.com/blog/python-automation//#python-examples)
    
-   [Taking automation to the next level](https://zapier.com/blog/python-automation//#automation)
    

**Related reading:** [Not sure when to automate a task? Start here.](https://zapier.com/blog/when-to-automate/)

## Why automate tasks with Python?

[<u class="css-0 e5612fr14">Automation</u>](https://zapier.com/blog/zapier-automation-examples/) lets you hand off business-critical tasks to the robots, so you can focus on the most important items on your to-do list—the ones that require active thought and engagement.

[<u class="css-0 e5612fr14">No-code automation</u>](https://zapier.com/blog/what-is-no-code/) should be your first stop, but Python's popularity for task automation comes from a variety of factors, including its:

-   **Simplicity and intuitiveness:** Compared to many other programming languages, Python is very easy to read and comprehend. While learning a language like C++ or Java can feel like learning a foreign language, Python syntax resembles English. 
    
-   **Support of data structures:** Python offers several ways to store data—including lists and dictionaries—and the ability to create your own data structures. This makes data management easy, improving automation responsiveness.
    
-   **Extensive automation capabilities:** Python comes equipped with a huge set of libraries that enable you to accomplish nearly any automation goal that comes to mind—machine learning, operating system management, and more. Plus, Python's support network is huge, so you should be able to find an answer to nearly any automation question online.
    

![](https://images.ctfassets.net/lzny33ho1g45/1EjxoQBenI4gFUsjWMEg8q/2d0d65c7992bb189c31f4b4a66701bba/pathon-automation-benefits__1_.png?w=1400)

## How to run a Python script

Before you start creating scripts, here's a little refresher on how to use Python. First, [<u class="css-0 e5612fr14">download Python</u>](https://www.python.org/downloads/) onto your device (for free!). Once you download it, you can create and run a script.

Your script file needs to be named with the extension `.py`, which stands for "Python." This tells your device that the file will contain Python code. You'll then add your script to this file and run it using your device's command-line or terminal.

After creating your file and opening your terminal, type `python3` followed by the path to your script. For example, on my Mac, I would:

1.  Create an empty text file called `FILE.py`.
    
2.  Add my script.
    
3.  Open the Terminal app.
    
4.  Type `python3`.
    
5.  Drag the file into the app, and press enter, which would run the script.
    

I created a simple script as an example. Here's what the file looks like:

![](https://images.ctfassets.net/lzny33ho1g45/4wHra7Rn91s3H6vqBW9KVu/a523825d1241358ee7fa817a1c16c37a/how-to-run-python-script.jpg?w=1400)

And here's what it looks like to execute the script in Terminal:

![](https://images.ctfassets.net/lzny33ho1g45/6e1tg8fixoqfcSCGzoIjCv/c6c1595bb14f0debcdce8beb19fe1f82/executing-script-in-terminal.jpg?w=1400)

If you're running one of the most recent versions of Windows, you should be able to type your .py file's name in the Windows Command Prompt and run it without first typing the `python3` command. And voilá—you're ready to get automating.

## 9 useful Python automation script examples

![](https://images.ctfassets.net/lzny33ho1g45/4qujZM3Tlye0pDZAYUU0v6/9d11de8e088192c493c2b918633aaea4/ways-to-automate-with-python.png?w=1400)

Uses of programming languages are practically unlimited, but nobody has time to learn every script there is. I've compiled nine Python automation ideas to simplify tasks that may otherwise distract you from important work, grouped into the following categories:

-   Interacting with APIs
    
-   Web scraping
    
-   Reformatting
    
-   Reading and writing files
    
-   Consolidating tasks
    
-   Organizing data
    

Running these scripts may require some preparatory steps, like downloading libraries. Follow the directions below, and you'll have Python completing tasks for you in no time.

### **Retrieve real-time data using APIs**

[<u class="css-0 e5612fr14">APIs</u>](https://zapier.com/learn/apis/) make it possible to retrieve real-time data from third parties. Traffic data is always changing, so it presents a great opportunity to work with an API. With Python, we can quickly pull live traffic data as long as we have the URL where the API collects the data. For this example, I used [<u class="css-0 e5612fr14">TomTom's</u>](https://www.tomtom.com/) API URL that enables access to live Los Angeles traffic data.

In the following script, I first install the _requests_ library in order to gather data from the URL, then unpack the URL as a JSON file.

**How it works**

This script uses the popular `requests` library, which allows Python to communicate with external services over HTTP. Here's a quick breakdown of what each part does:

-   **Install requests:** Before running the code, install the `requests` library by typing `pip install requests` in your terminal.
    
-   **Request data from the API:** The `get()` object sends a request to the specified URL (the API endpoint).
    
-   **Parse JSON data:** Once the response comes back, `json()` converts it to a JSON object, which Python can easily process.
    

**Example script: Pulling live traffic data**

In the following script, I first install the `requests` library in order to gather data from the URL, then unpack the URL as a JSON file.

| 
`pip install requests`

 |
| --- |

| 
`import requests`

`# Define the API URL for live traffic data in Los Angeles`

`url_api = 'https://api.midway.tomtom.com/ranking/liveHourly/USA_los-angeles'`

`usa_req = requests.get(url_api)`

`usa_json = usa_req.json()`

`# Output the data to verify the API response` 

`print(usa_json)`

 |
| --- |

Once you have the data in JSON format, you can parse specific elements to create meaningful outputs. For example, you could extract the current traffic congestion level or save the data to a file for later analysis. Here's an example of how you might use the JSON response:

| 
`# Extract a specific data point from the JSON response`

`if 'data' in usa_json:`

    `live_data = usa_json['data']`

    `print(f"Current traffic data: {live_data}")`

`else:`

    `print("Data not found in the API response.")`

 |
| --- |

### Extract data **with web scraping**

If your workday involves regularly pulling fresh data from the same websites, Python's [web scraping](https://zapier.com/blog/browse-ai/) capabilities can save you a lot of time. While it has specialized libraries to extract from specific sources like Wikipedia, the following script uses a more versatile web parsing and scraping library called [<u class="css-0 e5612fr14">Beautiful Soup</u>](https://www.crummy.com/software/BeautifulSoup/).

**How it works**

Web scraping involves two key steps: downloading a webpage's content and parsing the relevant data from it. In this example, we'll use:

-   **Requests library:** To fetch the HTML content of a webpage
    
-   **Beautiful Soup library:** To parse the HTML and extract specific elements, such as headlines, product prices, or images
    

This method allows you to retrieve only the data you need, eliminating the clutter of extraneous content. Here's a quick breakdown of the rest of the process:

1.  **Fetch page content:** `requests.get(URL)` sends a request to the target website. This checks if the request is successful (status code 200) and retrieves the HTML content.
    
2.  **Parse the HTML**: Beautiful Soup converts the raw HTML into a structured format that's easier to navigate.
    
3.  **Extract Specific Data**: Use methods like `soup.find_all(tag)` to target specific elements on the page, such as headlines or links. For our example, we'll pull all of the H2 headings.
    

**Example script: Extracting website headlines**

Use this script to pull today's headlines from the BBC News home page. But first, ensure you have the necessary libraries installed.

| 
`pip install requests`

`pip install beautifulsoup4`

 |
| --- |

| 
i`mport requests`

`from bs4 import BeautifulSoup`

`# URL of the webpage to scrape`

`url = 'https://www.bbc.com/news'`

`# Send a GET request to fetch the webpage content`

`response = requests.get(url)`

`# Check if the request was successful`

`if response.status_code == 200:`

    `# Parse the HTML content using BeautifulSoup`

    `soup = BeautifulSoup(response.content, 'html.parser')`

    `# Extract all H2 headlines from the page`

    `headlines = soup.find_all('h2')`

    `# Print each headline`

    `for headline in headlines:`

        `print(headline.text)`

`else:`

    `print(f"Failed to retrieve the page. Status code: {response.status_code}")`

 |
| --- |

Play around with the Beautiful Soup library to pull whatever data you need from a webpage with the punch of a command.

### Convert text to audio file

For the visually impaired (or for those of us who would rather listen to an audiobook than pick up a physical copy), Python offers libraries that make [text-to-speech](https://zapier.com/blog/best-text-dictation-software/) a breeze.

**How it works**

For this script, we'll be pulling from two Python libraries:

-   **PyPDF2:** A library that can read text from PDFs; it's versatile and handles multi-page documents effectively
    
-   **Pyttsx3:** A text-to-speech library that converts text into audio; it allows you to generate audio files with natural-sounding voices, which can be saved and replayed
    

Here's a breakdown of the process:

1.  **Extract text:** The `PyPDF2` library reads each page in the PDF and extracts its text content.
    
2.  **Text-to-speech conversion:** Using `Pyttsx3`, the script converts the extracted text into spoken audio.
    
3.  **Save as audio file:** The output audio is saved as an MP3 file, creating a standalone audio version of the PDF.
    

**Example script: Reformatting a PDF to MP3**

| 
`import pyttsx3`

`import PyPDF2`

`# Replace 'file.pdf' with the path to your PDF file (e.g., '/Desktop/Contracts/file.pdf')`

`pdf_reader = PyPDF2.PdfFileReader(open('file.pdf', 'rb'))`

`audio_reader = pyttsx3.init()`

`# Iterate through all pages in the PDF`

`for page in range(pdf_reader.numPages):`   

    `text = pdf_reader.getPage(page).extractText()`

    `# Clean up the text for better audio output`

    `legible_text = text.strip().replace('\n', ' ')`

    `print(legible_text)  # Optional: Print to see the text being processed`

    `# Convert the text to speech`

    `audio_reader.say(legible_text)`

`# Save the entire audio to an MP3 file`

`audio_reader.save_to_file(" ".join([pdf_reader.getPage(i).extractText().strip().replace('\n', ' ') for i in range(pdf_reader.numPages)]), 'file.mp3')`

`audio_reader.runAndWait()`

`audio_reader.stop()`

 |
| --- |

### **Reformat image file**

Converting between image formats is a tedious manual task, especially when dealing with multiple files. Python can automate this process, making it quick and efficient to convert images between formats. This is particularly useful when you need to prepare multiple images for web upload, standardize image formats across a project, or convert user-submitted images to a consistent format.

**How it works**

This script uses the **Pillow** library, a popular Python imaging library. Here's a quick overview:

1.  **Import required libraries:** For handling file paths and extensions, use `os`. `Image` from `PL` provides tools for opening, manipulating, and saving images.
    
2.  **Define a list of images:** `images = ['test.jpg']` contains the names of JPG files to be converted to PNG format. You can replace '`test.jpg`' with the file names you want to process.
    
3.  **Extract file names:** `os.path.splitext(infile)` separates the file name into `f` (the name without extension) and `e` (the extension). A new file name is created by appending `.png` to `f` (e.g., `test.png`).
    
4.  **Check for output duplication:** Ensure the input file (infile) is not the same as the output file (`outfile`).
    
5.  **Open and convert the image:** Image.open(infile) opens the JPG file for processing, while `image.save(outfile), 'PNG'` saves the opened image as a PNG file with the new file name.
    

**Example script: Converting a JPG to a PNG**

First, install the Pillow library if you haven't already:

| 
`pip install Pillow`

 |
| --- |

Then, use the following script to convert your JPG images to PNG:

| 
`import os`

`from PIL import Image`

`# List of images to convert`

`images = ['test.jpg']  # Replace with your image file names`

`for infile in images:`

    `f, e = os.path.splitext(infile)`

    `outfile = f + '.png'  # Change to desired output format`

    `if infile != outfile:`

        `try:`

            `with Image.open(infile) as image:`

                `image.save(outfile, 'PNG')  # Save as PNG`

                `print(f"Successfully converted {infile} to {outfile}")`

        `except OSError:`

            `print(f"Conversion failed for {infile}")`

 |
| --- |

### **Extract data from** a CSV

CSV (Comma Separated Values) is a common format for importing and exporting spreadsheets from programs like Excel. Python can read a CSV, meaning that it can copy and store its contents. Once Python reads the spreadsheet's contents, you can pull from these contents and use them to complete other tasks. For example, you can use this script to import customer information into your [<u class="css-0 e5612fr14">CRM system</u>](https://zapier.com/blog/best-crm-app/), analyze sales trends, or even feed data into other applications.

**How it works**

This script uses Python's built-in `csv` module, which makes it simple to read and manipulate CSV files. Here's what each part of the script does:

1.  **Open the file:** The `open()` function opens the specified file (`customers.csv`) in read mode.
    
2.  **Create a CSV reader:** The `csv.reader` object processes the file's contents and splits it into rows based on the specified delimiter (default is a comma).
    
3.  **Iterate through rows:** A loop goes through each row in the file and prints its contents, joining them with a comma for easy readability.
    

**Example script: Reading a CSV**

| 
`import csv`

`# Replace 'customers.csv' with your file path`

`file_path = 'customers.csv'`

`# Open and read the CSV file`

`with open(file_path, newline='') as csvfile:`

    `cust_reader = csv.reader(csvfile)`

    `# Process and print each row in the file`

    `for row in cust_reader:`

        `print(', '.join(row))`

 |
| --- |

### Modify data in a CSV

You can also modify an existing CSV file using Python's `write` feature. This replaces the contents in a CSV file without needing to enter new data manually. Learn more about how to read and write CSV files using Python's [<u class="css-0 e5612fr14">CSV library</u>](https://docs.python.org/3/library/csv.html).

**How it works**

This script demonstrates how to add a new row of data to an existing CSV file using Python's `csv` library. Here's a breakdown:

1.  **Data preparation:** The new row, `['James Smith', 'james@smith.com', 200000]`, is defined as a list of values.
    
2.  **File handling:** The `open()` function opens the `customers.csv` file in append mode (`'a'`), ensuring the new row is added without overwriting the file. If the file doesn't exist, it will be created.
    
3.  **Writing the data:** The `csv.writer()` object writes the new row to the file, with fields separated by commas and special characters properly quoted.
    
4.  **Confirmation:** After adding the row, a success message confirms the operation.
    

**Example script: Adding rows to a CSV**

| 
`import csv`

`Row = ['James Smith', 'james@smith.com', 200000]`

`# Make sure 'customers.csv' is in your root directory, or provide path to open() method.`

`# pass in 'a' to append new row or 'w' to overwrite CSV file`

`with open('customers.csv', 'a', newline='') as csvfile:`

    `cust_writer = csv.writer(csvfile, delimiter=',',`

                            `quotechar='|', quoting=csv.QUOTE_MINIMAL)`

    `cust_writer.writerow(Row)`

 |
| --- |

| 
`import csv`

`# Data to be added as a new row`

`new_row = ['James Smith', 'james@smith.com', 200000]`

`# Ensure 'customers.csv' is in your root directory or provide its full path`

`with open('customers.csv', 'a', newline='') as csvfile:`

    `cust_writer = csv.writer(csvfile, delimiter=',', quotechar='"', quoting=csv.QUOTE_MINIMAL)`

    `# Write the new row to the file`

    `cust_writer.writerow(new_row)`

`print("Row added successfully!")`

 |
| --- |

If you need to modify existing data instead of just appending it, you can first read the file into memory, edit the data as needed, and then write it back to the file:

| 
`import csv`

`# Read the existing CSV file into memory`

`rows = []`

`with open('customers.csv', 'r') as csvfile:`

    `cust_reader = csv.reader(csvfile)`

    `for row in cust_reader:`

        `# Example: Update the salary for 'James Smith'`

        `if row[0] == 'James Smith':`

            `row[2] = '250000'  # Updating the salary`

        `rows.append(row)`

`# Write the modified data back to the CSV file`

`with open('customers.csv', 'w', newline='') as csvfile:`

    `cust_writer = csv.writer(csvfile)`

    `cust_writer.writerows(rows)`

`print("CSV file updated successfully!")`

 |
| --- |

### Send personalized emails to multiple people

Nobody likes sending 30+ nearly identical emails, one-by-one. If you work in a field that requires this—marketing, education, or management, to name a few—Python makes this significantly easier. Start by creating a new CSV and filling it with all of your recipients' information, then run the script below.

**How it works**

This script uses Python's built-in `smtplib` for sending emails via Gmail's SMTP server and `csv` to read recipient information from a CSV file. Here's what each part does:

-   **SMTP (simple mail transfer protocol):** Handles the email-sending process securely
    
-   **CSV file:** Stores recipient information (name, email, and any custom data like scores), allowing the script to personalize each message
    
-   **Template message:** Uses placeholders to dynamically insert personalized information for each recipient
    

From there, the script:

1.  Reads recipient data from `customers.csv`
    
2.  Logs into Gmail securely using an app password
    
3.  Iterates through each row of the CSV to personalize and send an email
    

Each recipient will receive a unique email tailored with their information.

**Example script: Sending bulk emails with Gmail**

You may have to create an [<u class="css-0 e5612fr14">app password</u>](https://myaccount.google.com/apppasswords) for Gmail to run the script. If you notice the script doesn't run without one, create your password and enter it following the prompt `Enter password:` in the script.

![](https://images.ctfassets.net/lzny33ho1g45/653XJUsdnrwaviOKPpGxYE/b7564dc6b08ac27fd4d0fc06e489309d/app-passwords.png?w=1400)

| 
`import csv, smtplib, ssl`

`from datetime import date`

`# Get today's date for personalization`

`today = date.today().strftime('%B %d, %Y')`

`# Email template with placeholders for name, date, and score`

`message = '''Subject: Your Evaluation`

`Hi {name},`

`The date of your Q1 evaluation is {date}. Your score is: {score}.`

`'''`

`# Sender email address and app password`

`from_address = 'YOUR_EMAIL_ADDRESS'`

`# Create an app password here: https://myaccount.google.com/apppasswords`

`password = input('Enter password: ')`

`# Secure connection to Gmail's SMTP server`

`context = ssl.create_default_context()`

`# Open a secure session and send emails`

`with smtplib.SMTP_SSL('smtp.gmail.com', 465, context=context) as server:`

    `server.login(from_address, password)`

    `# Open and read recipient details from customers.csv`

    `with open('customers.csv') as file:`

        `reader = csv.reader(file)`

        `for name, email, score in reader:`

            `# Send personalized email`

            `server.sendmail(`

                `from_address,`

                `email,`

                `message.format(name=name, date=today, score=score),`

            `)`

 |
| --- |

### **Back up files to cloud storage**

While uploading a single file to the cloud likely isn't causing you a whole lot of grief, manually uploading tens or hundreds of files at a time can eat away at valuable time. Luckily, Python's `requests` library (which we've pulled from in earlier scripts) can simplify this process.

**How it works**

This script uses the `PyDrive` library to interact with [<u class="css-0 e5612fr14">Google Drive</u>](https://zapier.com/blog/how-to-use-google-drive/). The process involves two main steps—authenticating with Google Drive and uploading files. Here's a quick overview:

-   **Google Drive API setup:** You'll need to create a project in the Google Cloud Console and enable the Google Drive API. This setup allows Python to interact with your Google Drive securely.
    
-   **File uploading:** The script iterates over a list of files in your local directory and uploads them to a specified folder in your Google Drive.
    

**Example script: Bulk uploading to Google Drive**

In order for Google's authentication process to work, you'll need to set up a project and credentials in your [<u class="css-0 e5612fr14">Google Cloud Dashboard</u>](https://console.cloud.google.com/). Here's a quick overview of how to do this:

1.  In an existing or new Google Cloud Project, navigate to **Library** > Search "Google Drive API," and click **Enable**.
    
2.  Navigate to **Credentials** \> **\+ Create Credentials** > **OAuth client ID**
    
3.  Create a consent screen by providing the required fields. 
    
4.  Repeat step two, this time selecting _Application Type_ of **Desktop App**, and click **Create**.
    
5.  Download the auth JSON file, and place it in the root of the project alongside the .py script below. 
    

First, install the PyDrive library if you haven't already:

| 
`pip install pydrive`

 |
| --- |

Then, use the following script to upload your files:

| 
`from pydrive.auth import GoogleAuth`

`from pydrive.drive import GoogleDrive`

`# Authenticate with Google Drive`

`google_auth = GoogleAuth()`

`google_auth.LocalWebserverAuth()`

`drive_app = GoogleDrive(google_auth)`

`# List of files to upload`

`upload_list = ['test.png', 'test.jpg']`

`# Folder ID from Google Drive (replace 'FOLDER_ID_FROM_GOOGLE_DRIVE' with your folder's ID)`

`folder_id = 'FOLDER_ID_FROM_GOOGLE_DRIVE'`

`# Upload each file in the list`

`for file_to_upload in upload_list:`

    `file = drive_app.CreateFile({'parents': [{'id': folder_id}]})`

    `file.SetContentFile(file_to_upload)`

    `file.Upload()`

    `print(f"Uploaded {file_to_upload} successfully!")`

 |
| --- |

### Clean up your computer

If you're like me and [<u class="css-0 e5612fr14">your computer desktop looks like a warzone</u>](https://zapier.com/blog/how-to-clean-up-mac/), Python can help you organize your life in a matter of seconds.

**How it works**

We'll be using Python's `os` and `shutil` modules for this process, as they allow Python to make changes to your device's operating system—think renaming files, creating folders, etc.—and organize files.

Here's how this script works:

1.  **Create a destination folder:** The script creates a folder named "Everything" (or appends a number to avoid overwriting an existing folder).
    
2.  **List desktop files:** It identifies all files on the desktop, excluding the script file itself.
    
3.  **Move files:** The script moves the files into the "Everything" folder, tidying up your desktop.
    

**Example script: Cleaning up your desktop**

We're keeping it simple here, but feel free to play around with Python's `os` and `shutil` modules to better organize your files.

| 
`import os, shutil`

`# Initialize an empty list for files and a counter for folder names`

`lis = []`

`i = 1`

`# Define the destination folder path`

`destinationdir = '/Users/NAME/Desktop/Everything'`

`# Check if the folder already exists and create a unique name if needed`

`while os.path.exists(destinationdir):`

    `destinationdir += str(i)`

    `i += 1`

`os.makedirs(destinationdir)`

`# List all files on the desktop`

`lis = os.listdir('/Users/NAME/Desktop')`

`# Loop through files and move them to the destination folder`

`for x in lis:`

    `print(x)`

    `if x == __file__:  # Skip the script file itself`

        `continue`

    `shutil.move(x, destinationdir)`

 |
| --- |

## Taking automation to the next level with Zapier

Zapier is equipped to automate _a lot_ of processes—probably more than you know exist. But for those that aren't directly built into Zapier, you can use [<u class="css-0 e5612fr14">Code by Zapier</u>](https://zapier.com/apps/code/integrations) to create triggers and actions using JavaScript or Python. 

It's also very likely you can [<u class="css-0 e5612fr14">automate your workflows</u>](https://zapier.com/blog/workflow-automation/) without any code at all. Zapier lets you automate your business-critical work with a visual builder—no code required.

**Related reading:**
