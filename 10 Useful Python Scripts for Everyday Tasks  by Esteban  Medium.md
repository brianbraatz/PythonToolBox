---
Description: 10 Useful Python Scripts for Everyday Tasks 
Notes: 
author: Esteban
Url: https://medium.com/@estebanpiero/10-useful-python-scripts-for-everyday-tasks-b0d74f2ea62c
Created: "2025-01-28  09:32:15"
Modified: 
Tags:
---

# 10 Useful Python Scripts for Everyday Tasks | by Esteban | Medium

source: https://medium.com/@estebanpiero/10-useful-python-scripts-for-everyday-tasks-b0d74f2ea62c

> ## Excerpt
> Python is a versatile programming language known for its simplicity and readability. It’s widely used in various fields, from web development to data analysis. In this article, we’ll explore ten…

---
[

![Esteban](https://miro.medium.com/v2/resize:fill:83:83/1*B-ztlkhREbodukyE3NIaAw.png)



](https://medium.com/@estebanpiero?source=post_page---byline--b0d74f2ea62c--------------------------------)

Python is a versatile programming language known for its simplicity and readability. It’s widely used in various fields, from web development to data analysis. In this article, we’ll explore ten Python scripts that can make your life easier by automating common tasks.

![](https://miro.medium.com/v2/resize:fit:1313/1*zzF5_X3osuXQ5IB30pMzpg.png)

## 1\. Data Analysis with Pandas

[Pandas](https://pandas.pydata.org/) is a powerful library for data analysis and manipulation. With just a few lines of code, you can read, clean, and analyze data from various sources like CSV files or databases. Here’s a sample script:

```
<span id="ad7b" data-selectable-paragraph=""><mark><span>import</span></mark><mark> pandas </mark><mark><span>as</span></mark><mark> pd<br><br></mark><mark></mark><mark><br>data = pd.read_csv(</mark><mark><span>'data.csv'</span></mark><mark>)<br><br></mark><mark></mark><mark><br>mean = data[</mark><mark><span>'column_name'</span></mark><mark>].mean()<br></mark><mark><span>print</span></mark><mark>(</mark><mark><span>f"Mean: </span></mark><mark><span><span>{mean}</span></span></mark><mark><span>"</span></mark><mark>)</mark></span>
```

## 2\. Web Scraping with BeautifulSoup

[BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) is a Python library for web scraping. It allows you to extract data from websites with ease. Here’s a simple web scraping script:

```
<span id="b07b" data-selectable-paragraph=""><span>import</span> requests<br>from bs4 <span>import</span> BeautifulSoup<br><br>url = <span>'https://example.com'</span><br>response = requests.<span>get</span>(url)<br>soup = BeautifulSoup(response.text, <span>'html.parser'</span>)<br><br># Extract <span>data</span> from the webpage<br><span>data</span> = soup.find(<span>'div'</span>, class_=<span>'content'</span>)<br>print(<span>data</span>.text)</span>
```

## 3\. File Renamer

This script is handy when you need to rename multiple files in a folder based on specific criteria. For example, you can add a prefix, suffix, or replace text in filenames.

```
<span id="03a9" data-selectable-paragraph="">import <span>os</span><br><br>folder_path = <span>'/path/to/folder'</span><br><span>for</span> filename <span>in</span> <span>os</span>.listdir(folder_path):<br>    <span>if</span> filename.startswith(<span>'prefix_'</span>):<br>        new_filename = filename.replace(<span>'prefix_'</span>, <span>'new_prefix_'</span>)<br>        <span>os</span>.<span>rename</span>(<span>os</span>.<span>path</span>.join(folder_path, filename), <span>os</span>.<span>path</span>.join(folder_path, new_filename))</span>
```

## 4\. Image Resizer with Pillow

[Pillow](https://python-pillow.org/) is a Python Imaging Library that simplifies working with images. This script resizes a batch of images to a specified resolution or aspect ratio:

```
<span id="671e" data-selectable-paragraph="">from PIL import Image<br>import <span>os</span><br><br>input_folder = <span>'/path/to/images'</span><br>output_folder = <span>'/path/to/resized_images'</span><br>desired_size = (<span>100</span>, <span>100</span>)<br><br><span>for</span> filename <span>in</span> <span>os</span>.listdir(input_folder):<br>    with Image.<span>open</span>(<span>os</span>.<span>path</span>.join(input_folder, filename)) as img:<br>        img.thumbnail(desired_size)<br>        img.save(<span>os</span>.<span>path</span>.join(output_folder, filename))</span>
```

## 5\. PDF Generator with ReportLab

[ReportLab](https://www.reportlab.com/) is a library for creating PDF documents in Python. You can generate PDF files from text or HTML content. Here’s a basic example:

```
<span id="ee29" data-selectable-paragraph=""><span>from</span> reportlab.pdfgen import canvas<br><br>pdf_file = <br><span>text</span> = <br><br>c = canvas.Canvas(pdf_file)<br>c.drawString(<span>100</span>, <span>750</span>, <span>text</span>)<br>c.save()</span>
```

## 6\. Automated Email Sender with smtplib

Need to send automated emails? Python’s `smtplib` library can help. This script sends emails programmatically:

```
<span id="77ef" data-selectable-paragraph=""><span>import</span> smtplib<br><span>from</span> email.<span>mime</span>.<span>text</span> <span>import</span> <span>MIMEText</span><br><span>from</span> email.<span>mime</span>.<span>multipart</span> <span>import</span> <span>MIMEMultipart</span><br><br>smtp_server = <span>'smtp.example.com'</span><br>sender_email = <span>'your_email@example.com'</span><br>receiver_email = <span>'recipient@example.com'</span><br>password = <span>'your_password'</span><br><br>message = <span>MIMEMultipart</span>()<br>message[<span>'From'</span>] = sender_email<br>message[<span>'To'</span>] = receiver_email<br>message[<span>'Subject'</span>] = <span>'Sample Email Subject'</span><br><br>body = <span>'This is a sample email message.'</span><br>message.<span>attach</span>(<span>MIMEText</span>(body, <span>'plain'</span>))<br><br><span>with</span> smtplib.<span>SMTP</span>(smtp_server, <span>587</span>) <span>as</span> <span>server</span>:<br>    server.<span>starttls</span>()<br>    server.<span>login</span>(sender_email, password)<br>    server.<span>sendmail</span>(sender_email, receiver_email, message.<span>as_string</span>())</span>
```

## 7\. Data Backup Script

Automate the backup of files and directories to ensure data safety:

```
<span id="2b9a" data-selectable-paragraph=""><span>import</span> <span>shutil</span><br><br><span>source_folder</span> <span>=</span> <span>'/path/to/source_folder'</span><br>backup_folder = <span>'/path/to/backup_folder'</span><br><br>shutil.copytree(source_folder, backup_folder)</span>
```

## 8\. Password Generator

Generate strong and random passwords for improved security:

```
<span id="8b0c" data-selectable-paragraph=""><span>import</span> random<br><span>import</span> <span>string</span><br><br>def generate_password(length=<span>12</span>):<br>    characters = <span>string</span>.ascii_letters + <span>string</span>.digits + <span>string</span>.punctuation<br>    <span>return</span> <span>''</span>.join(random.choice(characters) <span>for</span> _ in <span>range</span>(length))<br><br>password = generate_password()<br><span>print</span>(password)</span>
```

## 9\. Simple Web Server

Create a basic HTTP server for testing and development:

```
<span id="a9c6" data-selectable-paragraph=""><span>import</span> http.server<br><span>import</span> socketserver<br><br>port = <span>8000</span><br><br><span>with</span> socketserver.TCPServer((<span>''</span>, port), http.server.SimpleHTTPRequestHandler) <span>as</span> httpd:<br>    <span>print</span>(<span>f"Serving at port <span>{port}</span>"</span>)<br>    httpd.serve_forever()</span>
```

## 10\. Database Backup and Restore using SQLite

SQLite is a C library that provides a lightweight disk-based database that doesn’t require a separate server process and allows accessing the database using a nonstandard variant of the SQL query language. Some applications can use SQLite for internal data storage. It’s also possible to prototype an application using SQLite and then port the code to a larger database such as PostgreSQL or Oracle.

Below, I’ll provide you with a sample code for backing up and restoring a SQLite database in Python, which is a lightweight and commonly used database system:

```
<span id="3f65" data-selectable-paragraph=""><span>import</span> sqlite3<br><span>import</span> shutil<br><br><br>source_db_file = <span>'source.db'</span><br>backup_db_file = <span>'backup.db'</span><br><br><br><span>def</span> <span>backup_database</span>():<br>    <span>try</span>:<br>        shutil.copy2(source_db_file, backup_db_file)<br>        <span>print</span>(<span>"Backup successful."</span>)<br>    <span>except</span> Exception <span>as</span> e:<br>        <span>print</span>(<span>f"Backup failed: <span>{<span>str</span>(e)}</span>"</span>)<br><br><br><span>def</span> <span>restore_database</span>():<br>    <span>try</span>:<br>        shutil.copy2(backup_db_file, source_db_file)<br>        <span>print</span>(<span>"Restore successful."</span>)<br>    <span>except</span> Exception <span>as</span> e:<br>        <span>print</span>(<span>f"Restore failed: <span>{<span>str</span>(e)}</span>"</span>)<br><br><br><span>while</span> <span>True</span>:<br>    <span>print</span>(<span>"Options:"</span>)<br>    <span>print</span>(<span>"1. Backup Database"</span>)<br>    <span>print</span>(<span>"2. Restore Database"</span>)<br>    <span>print</span>(<span>"3. Quit"</span>)<br>    choice = <span>input</span>(<span>"Enter your choice (1/2/3): "</span>)<br><br>    <span>if</span> choice == <span>'1'</span>:<br>        backup_database()<br>    <span>elif</span> choice == <span>'2'</span>:<br>        restore_database()<br>    <span>elif</span> choice == <span>'3'</span>:<br>        <span>break</span><br>    <span>else</span>:<br>        <span>print</span>(<span>"Invalid choice. Please enter 1, 2, or 3."</span>)</span>
```

In this code:

1.  `backup_database()` function makes a copy of the source SQLite database file and names it as the backup file. You can run this function to create backup of your database.
2.  `restore_database()` function copies the backup file back to the source file, effectively restoring the database to the state it was when the backup was created.
3.  The user is presented with options to either backup the database, restore it, or quit the program.
4.  You can adjust the `source_db_file` and `backup_db_file` variables to specify the paths to your SQLite source and backup database files.
