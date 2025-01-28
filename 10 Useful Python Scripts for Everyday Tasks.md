---
Description: 10 Useful Python Scripts for Everyday Tasks | by Esteban | Medium
Notes: Python is a versatile programming language known for its simplicity and readability. It’s widely used in various fields, from web development to data analysis. In this article, we’ll explore ten…
author: Esteban
Url: https://medium.com/@estebanpiero/10-useful-python-scripts-for-everyday-tasks-b0d74f2ea62c
Created: "2025-01-28  09:53:30"
Modified: 
Tags:
---

# 10 Useful Python Scripts for Everyday Tasks | by Esteban | Medium

source: https://medium.com/@estebanpiero/10-useful-python-scripts-for-everyday-tasks-b0d74f2ea62c

> ## Excerpt
> Python is a versatile programming language known for its simplicity and readability. It’s widely used in various fields, from web development to data analysis. In this article, we’ll explore ten…

---
# 10 Useful Python Scripts for Everyday Tasks

[

![Esteban](https://miro.medium.com/v2/resize:fill:83:83/1*B-ztlkhREbodukyE3NIaAw.png)





](https://medium.com/@estebanpiero?source=post_page---byline--b0d74f2ea62c--------------------------------)

[Esteban](https://medium.com/@estebanpiero?source=post_page---byline--b0d74f2ea62c--------------------------------)

·

[Follow](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2F_%2Fsubscribe%2Fuser%2F2cd901090b33&operation=register&redirect=https%3A%2F%2Fmedium.com%2F%40estebanpiero%2F10-useful-python-scripts-for-everyday-tasks-b0d74f2ea62c&user=Esteban&userId=2cd901090b33&source=post_page-2cd901090b33--byline--b0d74f2ea62c---------------------post_header-----------)

4 min read

·

Sep 18, 2023

[

](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2F_%2Fvote%2Fp%2Fb0d74f2ea62c&operation=register&redirect=https%3A%2F%2Fmedium.com%2F%40estebanpiero%2F10-useful-python-scripts-for-everyday-tasks-b0d74f2ea62c&user=Esteban&userId=2cd901090b33&source=---header_actions--b0d74f2ea62c---------------------clap_footer-----------)

67

4

[](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2F_%2Fbookmark%2Fp%2Fb0d74f2ea62c&operation=register&redirect=https%3A%2F%2Fmedium.com%2F%40estebanpiero%2F10-useful-python-scripts-for-everyday-tasks-b0d74f2ea62c&source=---header_actions--b0d74f2ea62c---------------------bookmark_footer-----------)

[

](https://medium.com/m/signin?actionUrl=https%3A%2F%2Fmedium.com%2Fplans%3Fdimension%3Dpost_audio_button%26postId%3Db0d74f2ea62c&operation=register&redirect=https%3A%2F%2Fmedium.com%2F%40estebanpiero%2F10-useful-python-scripts-for-everyday-tasks-b0d74f2ea62c&source=---header_actions--b0d74f2ea62c---------------------post_audio_button-----------)

Python is a versatile programming language known for its simplicity and readability. It’s widely used in various fields, from web development to data analysis. In this article, we’ll explore ten Python scripts that can make your life easier by automating common tasks.

![](https://miro.medium.com/v2/resize:fit:1313/1*zzF5_X3osuXQ5IB30pMzpg.png)

# 1\. Data Analysis with Pandas

[Pandas](https://pandas.pydata.org/) is a powerful library for data analysis and manipulation. With just a few lines of code, you can read, clean, and analyze data from various sources like CSV files or databases. Here’s a sample script:

```
<span id="ad7b" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph=""><mark class="wv ww ao"><span class="hljs-keyword">import</span></mark><mark class="wv ww ao"> pandas </mark><mark class="wv ww ao"><span class="hljs-keyword">as</span></mark><mark class="wv ww ao"> pd<br><br></mark><mark class="wv ww ao"><span class="hljs-comment"># Read data from a CSV file</span></mark><mark class="wv ww ao"><br>data = pd.read_csv(</mark><mark class="wv ww ao"><span class="hljs-string">'data.csv'</span></mark><mark class="wv ww ao">)<br><br></mark><mark class="wv ww ao"><span class="hljs-comment"># Perform basic analysis</span></mark><mark class="wv ww ao"><br>mean = data[</mark><mark class="wv ww ao"><span class="hljs-string">'column_name'</span></mark><mark class="wv ww ao">].mean()<br></mark><mark class="wv ww ao"><span class="hljs-built_in">print</span></mark><mark class="wv ww ao">(</mark><mark class="wv ww ao"><span class="hljs-string">f"Mean: </span></mark><mark class="wv ww ao"><span class="hljs-string"><span class="hljs-subst">{mean}</span></span></mark><mark class="wv ww ao"><span class="hljs-string">"</span></mark><mark class="wv ww ao">)</mark></span>
```

# 2\. Web Scraping with BeautifulSoup

[BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) is a Python library for web scraping. It allows you to extract data from websites with ease. Here’s a simple web scraping script:

```
<span id="b07b" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph=""><span class="hljs-keyword">import</span> requests<br>from bs4 <span class="hljs-keyword">import</span> BeautifulSoup<br><br>url = <span class="hljs-string">'https://example.com'</span><br>response = requests.<span class="hljs-keyword">get</span>(url)<br>soup = BeautifulSoup(response.text, <span class="hljs-string">'html.parser'</span>)<br><br># Extract <span class="hljs-keyword">data</span> from the webpage<br><span class="hljs-keyword">data</span> = soup.find(<span class="hljs-string">'div'</span>, class_=<span class="hljs-string">'content'</span>)<br>print(<span class="hljs-keyword">data</span>.text)</span>
```

# 3\. File Renamer

This script is handy when you need to rename multiple files in a folder based on specific criteria. For example, you can add a prefix, suffix, or replace text in filenames.

```
<span id="03a9" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph="">import <span class="hljs-built_in">os</span><br><br>folder_path = <span class="hljs-string">'/path/to/folder'</span><br><span class="hljs-keyword">for</span> filename <span class="hljs-keyword">in</span> <span class="hljs-built_in">os</span>.listdir(folder_path):<br>    <span class="hljs-keyword">if</span> filename.startswith(<span class="hljs-string">'prefix_'</span>):<br>        new_filename = filename.replace(<span class="hljs-string">'prefix_'</span>, <span class="hljs-string">'new_prefix_'</span>)<br>        <span class="hljs-built_in">os</span>.<span class="hljs-built_in">rename</span>(<span class="hljs-built_in">os</span>.<span class="hljs-built_in">path</span>.join(folder_path, filename), <span class="hljs-built_in">os</span>.<span class="hljs-built_in">path</span>.join(folder_path, new_filename))</span>
```

# 4\. Image Resizer with Pillow

[Pillow](https://python-pillow.org/) is a Python Imaging Library that simplifies working with images. This script resizes a batch of images to a specified resolution or aspect ratio:

```
<span id="671e" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph="">from PIL import Image<br>import <span class="hljs-built_in">os</span><br><br>input_folder = <span class="hljs-string">'/path/to/images'</span><br>output_folder = <span class="hljs-string">'/path/to/resized_images'</span><br>desired_size = (<span class="hljs-number">100</span>, <span class="hljs-number">100</span>)<br><br><span class="hljs-keyword">for</span> filename <span class="hljs-keyword">in</span> <span class="hljs-built_in">os</span>.listdir(input_folder):<br>    with Image.<span class="hljs-built_in">open</span>(<span class="hljs-built_in">os</span>.<span class="hljs-built_in">path</span>.join(input_folder, filename)) as img:<br>        img.thumbnail(desired_size)<br>        img.save(<span class="hljs-built_in">os</span>.<span class="hljs-built_in">path</span>.join(output_folder, filename))</span>
```

# 5\. PDF Generator with ReportLab

[ReportLab](https://www.reportlab.com/) is a library for creating PDF documents in Python. You can generate PDF files from text or HTML content. Here’s a basic example:

```
<span id="ee29" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph=""><span class="hljs-keyword">from</span> reportlab.pdfgen import canvas<br><br>pdf_file = <span class="hljs-comment">'output.pdf'</span><br><span class="hljs-keyword">text</span> = <span class="hljs-comment">'Hello, this is a sample PDF.'</span><br><br>c = canvas.Canvas(pdf_file)<br>c.drawString(<span class="hljs-number">100</span>, <span class="hljs-number">750</span>, <span class="hljs-keyword">text</span>)<br>c.save()</span>
```

# 6\. Automated Email Sender with smtplib

Need to send automated emails? Python’s `smtplib` library can help. This script sends emails programmatically:

```
<span id="77ef" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph=""><span class="hljs-keyword">import</span> smtplib<br><span class="hljs-keyword">from</span> email.<span class="hljs-property">mime</span>.<span class="hljs-property">text</span> <span class="hljs-keyword">import</span> <span class="hljs-title.class">MIMEText</span><br><span class="hljs-keyword">from</span> email.<span class="hljs-property">mime</span>.<span class="hljs-property">multipart</span> <span class="hljs-keyword">import</span> <span class="hljs-title.class">MIMEMultipart</span><br><br>smtp_server = <span class="hljs-string">'smtp.example.com'</span><br>sender_email = <span class="hljs-string">'your_email@example.com'</span><br>receiver_email = <span class="hljs-string">'recipient@example.com'</span><br>password = <span class="hljs-string">'your_password'</span><br><br>message = <span class="hljs-title.class">MIMEMultipart</span>()<br>message[<span class="hljs-string">'From'</span>] = sender_email<br>message[<span class="hljs-string">'To'</span>] = receiver_email<br>message[<span class="hljs-string">'Subject'</span>] = <span class="hljs-string">'Sample Email Subject'</span><br><br>body = <span class="hljs-string">'This is a sample email message.'</span><br>message.<span class="hljs-title.function">attach</span>(<span class="hljs-title.class">MIMEText</span>(body, <span class="hljs-string">'plain'</span>))<br><br><span class="hljs-keyword">with</span> smtplib.<span class="hljs-title.function">SMTP</span>(smtp_server, <span class="hljs-number">587</span>) <span class="hljs-keyword">as</span> <span class="hljs-attr">server</span>:<br>    server.<span class="hljs-title.function">starttls</span>()<br>    server.<span class="hljs-title.function">login</span>(sender_email, password)<br>    server.<span class="hljs-title.function">sendmail</span>(sender_email, receiver_email, message.<span class="hljs-title.function">as_string</span>())</span>
```

# 7\. Data Backup Script

Automate the backup of files and directories to ensure data safety:

```
<span id="2b9a" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph=""><span class="hljs-keyword">import</span> <span class="hljs-type">shutil</span><br><br><span class="hljs-variable">source_folder</span> <span class="hljs-operator">=</span> <span class="hljs-string">'/path/to/source_folder'</span><br>backup_folder = <span class="hljs-string">'/path/to/backup_folder'</span><br><br>shutil.copytree(source_folder, backup_folder)</span>
```

# 8\. Password Generator

Generate strong and random passwords for improved security:

```
<span id="8b0c" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph=""><span class="hljs-keyword">import</span> random<br><span class="hljs-keyword">import</span> <span class="hljs-type">string</span><br><br>def generate_password(length=<span class="hljs-number">12</span>):<br>    characters = <span class="hljs-type">string</span>.ascii_letters + <span class="hljs-type">string</span>.digits + <span class="hljs-type">string</span>.punctuation<br>    <span class="hljs-keyword">return</span> <span class="hljs-string">''</span>.join(random.choice(characters) <span class="hljs-keyword">for</span> _ in <span class="hljs-keyword">range</span>(length))<br><br>password = generate_password()<br><span class="hljs-built_in">print</span>(password)</span>
```

# 9\. Simple Web Server

Create a basic HTTP server for testing and development:

```
<span id="a9c6" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph=""><span class="hljs-keyword">import</span> http.server<br><span class="hljs-keyword">import</span> socketserver<br><br>port = <span class="hljs-number">8000</span><br><br><span class="hljs-keyword">with</span> socketserver.TCPServer((<span class="hljs-string">''</span>, port), http.server.SimpleHTTPRequestHandler) <span class="hljs-keyword">as</span> httpd:<br>    <span class="hljs-built_in">print</span>(<span class="hljs-string">f"Serving at port <span class="hljs-subst">{port}</span>"</span>)<br>    httpd.serve_forever()</span>
```

# 10\. Database Backup and Restore using SQLite

SQLite is a C library that provides a lightweight disk-based database that doesn’t require a separate server process and allows accessing the database using a nonstandard variant of the SQL query language. Some applications can use SQLite for internal data storage. It’s also possible to prototype an application using SQLite and then port the code to a larger database such as PostgreSQL or Oracle.

Below, I’ll provide you with a sample code for backing up and restoring a SQLite database in Python, which is a lightweight and commonly used database system:

```
<span id="3f65" class="pj oc gu pg b bg pk pl l pm pn" data-selectable-paragraph=""><span class="hljs-keyword">import</span> sqlite3<br><span class="hljs-keyword">import</span> shutil<br><br><span class="hljs-comment"># Database file paths</span><br>source_db_file = <span class="hljs-string">'source.db'</span><br>backup_db_file = <span class="hljs-string">'backup.db'</span><br><br><span class="hljs-comment"># Function to create a backup of the SQLite database</span><br><span class="hljs-keyword">def</span> <span class="hljs-title.function">backup_database</span>():<br>    <span class="hljs-keyword">try</span>:<br>        shutil.copy2(source_db_file, backup_db_file)<br>        <span class="hljs-built_in">print</span>(<span class="hljs-string">"Backup successful."</span>)<br>    <span class="hljs-keyword">except</span> Exception <span class="hljs-keyword">as</span> e:<br>        <span class="hljs-built_in">print</span>(<span class="hljs-string">f"Backup failed: <span class="hljs-subst">{<span class="hljs-built_in">str</span>(e)}</span>"</span>)<br><br><span class="hljs-comment"># Function to restore the SQLite database from a backup</span><br><span class="hljs-keyword">def</span> <span class="hljs-title.function">restore_database</span>():<br>    <span class="hljs-keyword">try</span>:<br>        shutil.copy2(backup_db_file, source_db_file)<br>        <span class="hljs-built_in">print</span>(<span class="hljs-string">"Restore successful."</span>)<br>    <span class="hljs-keyword">except</span> Exception <span class="hljs-keyword">as</span> e:<br>        <span class="hljs-built_in">print</span>(<span class="hljs-string">f"Restore failed: <span class="hljs-subst">{<span class="hljs-built_in">str</span>(e)}</span>"</span>)<br><br><span class="hljs-comment"># Usage</span><br><span class="hljs-keyword">while</span> <span class="hljs-literal">True</span>:<br>    <span class="hljs-built_in">print</span>(<span class="hljs-string">"Options:"</span>)<br>    <span class="hljs-built_in">print</span>(<span class="hljs-string">"1. Backup Database"</span>)<br>    <span class="hljs-built_in">print</span>(<span class="hljs-string">"2. Restore Database"</span>)<br>    <span class="hljs-built_in">print</span>(<span class="hljs-string">"3. Quit"</span>)<br>    choice = <span class="hljs-built_in">input</span>(<span class="hljs-string">"Enter your choice (1/2/3): "</span>)<br><br>    <span class="hljs-keyword">if</span> choice == <span class="hljs-string">'1'</span>:<br>        backup_database()<br>    <span class="hljs-keyword">elif</span> choice == <span class="hljs-string">'2'</span>:<br>        restore_database()<br>    <span class="hljs-keyword">elif</span> choice == <span class="hljs-string">'3'</span>:<br>        <span class="hljs-keyword">break</span><br>    <span class="hljs-keyword">else</span>:<br>        <span class="hljs-built_in">print</span>(<span class="hljs-string">"Invalid choice. Please enter 1, 2, or 3."</span>)</span>
```

In this code:

1.  `backup_database()` function makes a copy of the source SQLite database file and names it as the backup file. You can run this function to create backup of your database.
2.  `restore_database()` function copies the backup file back to the source file, effectively restoring the database to the state it was when the backup was created.
3.  The user is presented with options to either backup the database, restore it, or quit the program.
4.  You can adjust the `source_db_file` and `backup_db_file` variables to specify the paths to your SQLite source and backup database files.
