---
Description: 35 Python script examples | FOSS Linux
Notes: This article explains 35 python script examples using straightforward examples to help you learn Python's fundamentals. This article is for those new to Python.
author: By                                         Humphrey
Url: https://www.fosslinux.com/46256/python-script-examples.htm
Created: "2025-01-28  09:44:06"
Modified: 
Tags:
---

# 35 Python script examples | FOSS Linux

source: https://www.fosslinux.com/46256/python-script-examples.htm

> ## Excerpt
> This article explains 35 python script examples using straightforward examples to help you learn Python's fundamentals. This article is for those new to Python.

---
# 35 Python script examples

by [Humphrey](https://www.fosslinux.com/author/linuxauthor3) April 6, 2021

By [Humphrey](https://www.fosslinux.com/author/linuxauthor3) April 6, 2021

[![35 Python Script examples](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/35-Python-Script-examples.png?lossy=2&strip=1&webp=1 "35 Python Script examples")](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/35-Python-Script-examples.png?lossy=2&strip=1&webp=1)

_13.6K_

Python is a common and in-demand programming language these days because it can create applications ranging from easy to complex. This article is for those new to Python programming and want to learn it from the ground up in a short amount of time.

## Python script examples

This article explains 35 python script examples using straightforward examples to help you learn Python’s fundamentals.

### Create and run the first python script

You don’t need to create a python file to write and run a simple python script from the terminal. You can simply access the python console and run it there directly. To access the python console, open the terminal (Ctrl +Alt + T on ubuntu) and run the ‘python’ or ‘python3’ commands to open Python in interaction mode and execute any script from the terminal.

```
tuts@fosslinux:~$ python3
```

If the script is long, it will need to be written and saved in a python file using any editor. To write the script, you can use any text editor or code editor, such as PyCharm, sublime, Spyder, Visual Studio Code, or any IDE program designed specifically for Python.

<iframe class="powerIgnore" id="ifr_pw_14922_1" src="about:blank" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" topmargin="0" leftmargin="0" allowtransparency="true" width="728" height="100" sandbox="allow-forms allow-pointer-lock allow-popups allow-popups-to-escape-sandbox allow-scripts allow-same-origin allow-top-navigation-by-user-activation" style="width: 728px; height: 90px;"></iframe>

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_14922") })

 ![](https://ul.pubpowerplatform.io/assets/img/thumb_438549ac03493a190662504a4ca9d920.png)Next Stay Synthesize Beautiful Scenes of Ha Giang Via Super Quality Travel Video - Flycam Nem TV 40 42  ![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-white-100x18.png) 00:00  00:00 / 00:00 10 Sec<iframe id="powerRelatedIframe_pw_14950_1_instream" frameborder="0" scrolling="no" style="border: none; margin: 0px; overflow: hidden; position: absolute; top: 0px; left: 0px; max-width: 100%; min-width: 100%; width: 100%; z-index: 0 !important; height: 530px;"></iframe>

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.initPowerInstream("pw\_14950"); });

The python file has the .py extension.

The python scripts in this article are written using Python 3.9 and the Python PyCharm IDE. To use it, you must first install the PyCharm IDE on your device. Thus, this article’s demo scripts will be saved with a .py extension and triggered using the python3 command followed by the script’s name on the terminal. For instance,

```
python3 example_script.py
```

#### 1\. Pig Latin Translator script

A pig Latin refers to a combination of rules that changes the text in a particular language to make it difficult to understand for someone who is not trained.

Save the script to a file called latin\_translator.py with the following code.

```
# latin_translator.py&nbsp;

#request user for input
user_input = input("Input text to translate to pig latin: ")
print("User Text: ", user_input)

# This step breaks the words into a list
updated_user_input = user_input.split(' ')

for j in updated_user_input:
 if len(j) &gt;= 3: #only translate words with more than 3 characters
  j = j + "%say" % (j[0]) 
  j = j[1:]
  print(j)
 else:
  pass
```

To execute latin\_translator.py from the terminal, type the following code.

```
python3 latin_translator.py
```

After running the code, the terminal will display the following output.

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_11584") })

![Pig Latin Translator script](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Pig-Latin-Translator-script.png?lossy=2&strip=1&webp=1)

Pig Latin Translator script

#### 2\. Script to Reverse a Number

The script seeks to reverse the value of a number. In this case, the solution entails:

1\. Take the integer’s value and store it in a variable.  
2\. Get each digit of the number and store the reversed number in another variable using a while loop.  
3\. Write the number backward.  
4\. Get out of there.

Save the script to a file called reverse\_number.py with the following code.

```
# reverse_number.py

user_input=int(input("Enter the number to reverse: "))
_rev=0
while(user_input&gt;0):
  dig=user_input%10
  _rev=_rev*10+dig
  user_input=user_input//10
print("The reversed number is :",_rev)
```

After running the code, the terminal will display the following output.

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_15219") })

![Script to Reverse a Number](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Script-to-Reverse-a-Number.png?lossy=2&strip=1&webp=1)

Script to Reverse a Number

#### 3\. Joining two strings

In Python, there are a variety of ways to join string values. This is called string concatenation.

The ‘+’ operator is the simplest way to combine two string values in Python.

To learn how to connect two strings, build a python script with the following script.

Two string values are allocated to two variables, with a third variable used to store the joined values, which will be printed later.

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16024") })

Save the script to a file called join\_strings.py with the following code.

```
# join_strings.py

string1 = "my"
string2 = "work"

joined_string = string1 +string2

print(joined_string)
```

After running the script, the following output will appear.

![Joining two strings](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Joining-two-strings.png?lossy=2&strip=1&webp=1)

Joining two strings

The words “my” and “work” are combined here, and the result is “mywork”

#### 4\. In a given range, print odd numbers

This is an automation process that would otherwise be tedious and time-consuming to complete manually. The software prints all odd numbers within a given range using the upper and lower limits.

<ins class="adsbygoogle" style="display: block; text-align: center; height: 200px;" data-ad-layout="in-article" data-ad-format="fluid" data-ad-client="ca-pub-4052130819365638" data-ad-slot="5520628523" data-adsbygoogle-status="done" data-ad-status="filled"><div id="aswift_1_host" style="border: none; height: 200px; width: 890px; margin: 0px; padding: 0px; position: relative; visibility: visible; background-color: transparent; display: inline-block;"><iframe id="aswift_1" name="aswift_1" browsingtopics="true" style="left:0;position:absolute;top:0;border:0;width:890px;height:200px;" sandbox="allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation" width="890" height="200" frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" allow="attribution-reporting; run-ad-auction" src="https://googleads.g.doubleclick.net/pagead/ads?client=ca-pub-4052130819365638&amp;output=html&amp;h=200&amp;slotname=5520628523&amp;adk=982650690&amp;adf=1231662468&amp;pi=t.ma~as.5520628523&amp;w=890&amp;abgtt=6&amp;fwrn=4&amp;lmt=1738086210&amp;rafmt=11&amp;format=890x200&amp;url=https%3A%2F%2Fwww.fosslinux.com%2F46256%2Fpython-script-examples.htm&amp;wgl=1&amp;uach=WyJXaW5kb3dzIiwiMTUuMC4wIiwieDg2IiwiIiwiMTMyLjAuNjgzNC4xMTEiLG51bGwsMCxudWxsLCI2NCIsW1siTm90IEEoQnJhbmQiLCI4LjAuMC4wIl0sWyJDaHJvbWl1bSIsIjEzMi4wLjY4MzQuMTExIl0sWyJHb29nbGUgQ2hyb21lIiwiMTMyLjAuNjgzNC4xMTEiXV0sMF0.&amp;dt=1738086209170&amp;bpp=5&amp;bdt=619202&amp;idt=752&amp;shv=r20250122&amp;mjsv=m202501230101&amp;ptt=9&amp;saldr=aa&amp;abxe=1&amp;cookie_enabled=1&amp;eoidce=1&amp;prev_fmts=0x0&amp;nras=1&amp;correlator=4579272753827&amp;frm=20&amp;pv=1&amp;rplot=4&amp;u_tz=-480&amp;u_his=1&amp;u_h=960&amp;u_w=1536&amp;u_ah=912&amp;u_aw=1536&amp;u_cd=24&amp;u_sd=1.25&amp;dmc=8&amp;adx=125&amp;ady=4497&amp;biw=1519&amp;bih=791&amp;scr_x=0&amp;scr_y=1900&amp;eid=42531705%2C95332924&amp;oid=2&amp;pvsid=2903094197176072&amp;tmod=1724388224&amp;uas=3&amp;nvt=1&amp;ref=https%3A%2F%2Fwww.google.com%2F&amp;fc=1920&amp;brdim=0%2C0%2C0%2C0%2C1536%2C0%2C1536%2C912%2C1536%2C791&amp;vis=1&amp;rsz=%7C%7CoEebr%7C&amp;abl=CS&amp;pfx=0&amp;fu=128&amp;bc=31&amp;bz=1&amp;td=1&amp;tdf=2&amp;psd=W251bGwsW251bGwsbnVsbCxudWxsLCJkZXByZWNhdGVkX2thbm9uIl0sbnVsbCwzXQ..&amp;nt=1&amp;ifi=2&amp;uci=a!2&amp;btvi=1&amp;fsb=1&amp;dtd=1006" data-google-container-id="a!2" tabindex="0" title="Advertisement" aria-label="Advertisement" data-google-query-id="CM-y6Nn7mIsDFelFwgUdmMEFhA" data-load-complete="true"></iframe></div></ins>(adsbygoogle = window.adsbygoogle || \[\]).push({});

The solution to the Issue:

1.  Take the upper and lower range limits and store them separately in variables.
2.  Build a for-loop that covers the lower to upper range limits.
3.  Finally, use an if statement to determine if the number is odd or even, and then print the result.
4.  exit

Save the script to a file called print\_odd\_numbers.py with the following code.

```
# print_odd_numbers.py

lower_limit=int(input("Enter the lower limit for the range:"))
upper_limit=int(input("Enter the upper limit for the range:"))
for j in range(lower_limit,upper_limit+1):
if(j%2!=0):
print(j)
```

<ins data-ad-format="auto" class="adsbygoogle adsbygoogle-noablate" data-ad-client="ca-pub-4052130819365638" data-adsbygoogle-status="done" style="display: block; margin: auto; background-color: transparent; height: 280px;" data-ad-status="filled"><div id="aswift_3_host" style="border: none; height: 280px; width: 890px; margin: 0px; padding: 0px; position: relative; visibility: visible; background-color: transparent; display: inline-block; overflow: visible;"><iframe id="aswift_3" name="aswift_3" browsingtopics="true" style="left:0;position:absolute;top:0;border:0;width:890px;height:280px;" sandbox="allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation" width="890" height="280" frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" allow="attribution-reporting; run-ad-auction" src="https://googleads.g.doubleclick.net/pagead/ads?gdpr=0&amp;client=ca-pub-4052130819365638&amp;output=html&amp;h=280&amp;adk=1858194040&amp;adf=1970872&amp;pi=t.aa~a.3612172100~i.88~rp.4&amp;w=890&amp;abgtt=6&amp;fwrn=4&amp;fwrnh=100&amp;lmt=1738086215&amp;num_ads=1&amp;rafmt=1&amp;armr=3&amp;sem=mc&amp;pwprc=8508781010&amp;ad_type=text_image&amp;format=890x280&amp;url=https%3A%2F%2Fwww.fosslinux.com%2F46256%2Fpython-script-examples.htm&amp;fwr=0&amp;pra=3&amp;rh=200&amp;rw=889&amp;rpe=1&amp;resp_fmts=3&amp;wgl=1&amp;fa=27&amp;uach=WyJXaW5kb3dzIiwiMTUuMC4wIiwieDg2IiwiIiwiMTMyLjAuNjgzNC4xMTEiLG51bGwsMCxudWxsLCI2NCIsW1siTm90IEEoQnJhbmQiLCI4LjAuMC4wIl0sWyJDaHJvbWl1bSIsIjEzMi4wLjY4MzQuMTExIl0sWyJHb29nbGUgQ2hyb21lIiwiMTMyLjAuNjgzNC4xMTEiXV0sMF0.&amp;dt=1738086211382&amp;bpp=40&amp;bdt=621414&amp;idt=40&amp;shv=r20250122&amp;mjsv=m202501230101&amp;ptt=9&amp;saldr=aa&amp;abxe=1&amp;cookie=ID%3D95e85c93b8bff894%3AT%3D1738086211%3ART%3D1738086211%3AS%3DALNI_MaoFNRl48_2-kmJjF5jLvtf4tIn_w&amp;gpic=UID%3D00001036bf80cc86%3AT%3D1738086211%3ART%3D1738086211%3AS%3DALNI_MYBbxPVdFMnRS-dqYKMQG2eHPKoCA&amp;eo_id_str=ID%3D7f3c56aae6dd8bb2%3AT%3D1738086211%3ART%3D1738086211%3AS%3DAA-AfjYdLDVVD-2u94Lcf7VkHCDG&amp;prev_fmts=0x0%2C890x200&amp;nras=2&amp;correlator=4579272753827&amp;frm=20&amp;pv=1&amp;u_tz=-480&amp;u_his=1&amp;u_h=960&amp;u_w=1536&amp;u_ah=912&amp;u_aw=1536&amp;u_cd=24&amp;u_sd=1.25&amp;dmc=8&amp;adx=125&amp;ady=6583&amp;biw=1519&amp;bih=791&amp;scr_x=0&amp;scr_y=14845&amp;eid=42531705%2C95332924&amp;oid=2&amp;psts=AOrYGslOte8p5kvgZN4h32AKlVc9dvXFo40RqYKVcR-CsoQWSVnIlH7AUSTze46vVf2iWgmNq062a-tZSScPCA&amp;pvsid=2903094197176072&amp;tmod=1724388224&amp;uas=1&amp;nvt=1&amp;ref=https%3A%2F%2Fwww.google.com%2F&amp;fc=1408&amp;brdim=0%2C0%2C0%2C0%2C1536%2C0%2C1536%2C912%2C1536%2C791&amp;vis=1&amp;rsz=%7C%7Cs%7C&amp;abl=NS&amp;fu=128&amp;bc=31&amp;bz=1&amp;td=1&amp;tdf=2&amp;psd=W251bGwsW251bGwsbnVsbCxudWxsLCJkZXByZWNhdGVkX2thbm9uIl0sbnVsbCwzXQ..&amp;nt=1&amp;ifi=4&amp;uci=a!4&amp;fsb=1&amp;dtd=4202" data-google-container-id="a!4" tabindex="0" title="Advertisement" aria-label="Advertisement" data-google-query-id="CK6OtNz7mIsDFSVFwgUdi3Mlgg" data-load-complete="true"></iframe></div></ins>

After running the script, the following output will appear.

![In a given range, print odd numbers](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/In-a-given-range-print-odd-numbers.png?lossy=2&strip=1&webp=1)

In a given range, print odd numbers

#### 5: Format a floating-point number in a string

Programming requires floating-point numbers to generate fractional numbers, and formatting the floating-point number for programming purposes is often necessary.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16025") })

In Python, there are various ways to format a floating-point number. The following script formats a floating-point number using string formatting and string interpolation.

In string formatting, the format() method with format width is used, and string interpolation uses the “percent” symbol with the format with width.

Five digits are set before the decimal point, and two digits are set after the decimal point, according to the formatting distance.

Save the script to a file called floating\_point\_number.py with the following code.

Also Read

-   [Running JavaScript in the Linux Terminal](https://www.fosslinux.com/132860/running-javascript-in-the-linux-terminal.htm)
-   [10 Essential Python Run Command Usages You Need to Know](https://www.fosslinux.com/139347/essential-python-run-command-uses.htm)
-   [How to work with Files in Python](https://www.fosslinux.com/43689/how-to-work-with-files-in-python.htm)

```
# floating_point_number.py

# application of String Formatting 
first_val= 365.48951
print("String Formatting : {:5.2f}".format(first_val))

# application of String Interpolation
second_val= 365.48951
print("String Interpolation: %5.2f" % second_val)
```

After executing, the output will appear as follows.

![Format a floating-point number in a string](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Format-a-floating-point-number-in-a-string.png?lossy=2&strip=1&webp=1)

Format a floating-point number in a string

#### 6\. Raise a number by a factor

There are many ways to measure the x^n in Python. Three methods for calculating x^n in Python are shown in the script below.

The x^n is calculated using the double ‘\*’ operator, the pow() method, and the math.pow() method. Numeric values are used to initialize the values of x and n.

The methods double ‘\*’ and pow() are used to calculate integer values’ power. math.pow() can be used to measure the power of fractional numbers, as seen in the script’s final section.

Save the script to a file called raise\_number\_factor.py with the following code.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16028") })

```
# raise_number_factor.py

import math

# initialize x and n with values
x = 4
n = 3

# approach 1
result_val = x ** n
print("%d raised to the power %d is %d" % (x,n,result_val))

# approach 2
result_val = pow(x,n)
print("%d raised to the power %d is %d" % (x,n,result_val))

# approach 3
result_val = math.pow(x,n)
print("%d raised to the power %d is %5.2f" % (x,n,result_val))
```

After running the script, the following output will appear.

![Raise a number by a factor](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Raise-a-number-by-a-factor.png?lossy=2&strip=1&webp=1)

Raise a number by a factor

#### 7\. Working with Boolean types

The following script demonstrates the various uses of Boolean types. The value ‘value\_one’ will be printed in the first output, which is the Boolean value valid. Here, only zero returns false as a Boolean value, while all positive and negative numbers return true.

On the other hand, the second and third outputs will print real for both positive and negative numbers.

Since the comparison operator returns false, the fourth output will print false for 0, and the fifth output will also print false.

Save the script to a file called boolean\_types.py with the following code.

Also Read

-   [How to install multiple versions of GCC and G++ on Ubuntu 20.04](https://www.fosslinux.com/39386/how-to-install-multiple-versions-of-gcc-and-g-on-ubuntu-20-04.htm)
-   [10 Essential Python Run Command Usages You Need to Know](https://www.fosslinux.com/139347/essential-python-run-command-uses.htm)
-   [Python For Loop: Everything You Need to Know](https://www.fosslinux.com/42612/python-for-loop-everything-you-need-to-know.htm)

```
# boolean_types.py

# Boolean value
value_one = True
print("boolean value: ",value_one)

# Number to Boolean
number_to_boolean = 10
print("number to boolean: ",bool(number_to_boolean))

num_val = -5
print("negative number: ",bool(num_val))

num_val = 0
print("number is equal to zero: ",bool(num_val))

# Boolean from comparison operator
val_1 = 6
val_2 = 3
print("boolean from comparison operator: ", val_1 &lt; val_2)
```

After running the script, the following output will appear.

![Working with Boolean types](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Working-with-Boolean-types.png?lossy=2&strip=1&webp=1)

Working with Boolean types

8\. Usage of a conditional statement, if-else

The following script demonstrates how to use a conditional statement, if-else, in Python. Note that in Python, the if-else argument is declared a little differently than in other languages.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16029") })

In Python, unlike other languages, curly brackets are not needed to define the if-else block, but the indentation block must be used correctly, or the script will fail.

The script uses a simple if-else argument to verify if the number variable’s value is greater than or equal to 70 or not. After the if and else blocks, a colon(:) is used to mark the block’s beginning.

Save the script to a file called conditional\_if\_else.py with the following code.

```
# conditional_if_else.py


# initialize num_val with a numeric value
num_val = 40

# Check if num_val is more than 50 or not
if (num_val &gt; 50):
  print("you scored above average")
else:
  print("You scored below average")
```

After running the script, the following output will appear.

![Usage of a conditional statement, if-else](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Usage-of-a-conditional-statement-if-else.png?lossy=2&strip=1&webp=1)

Usage of a conditional statement, if-else

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16030") })

#### 9\. Usage of AND and OR operators in a conditional statement

The following script illustrates how to use AND and OR operators in a conditional statement.

The AND operator returns true if both conditions are true, and the OR operator returns true if either of the two conditions is true. As practical and theory signs, two floating-point numbers will be used.

The if the argument uses both AND and OR operators.

Also Read

-   [How to Update and Manage Python Versions on Linux](https://www.fosslinux.com/143798/how-to-update-and-manage-python-versions-on-linux.htm)
-   [Mastering the SQLite Database in Python](https://www.fosslinux.com/42799/mastering-the-sqlite-database-in-python.htm)
-   [How to install multiple versions of GCC and G++ on Ubuntu 20.04](https://www.fosslinux.com/39386/how-to-install-multiple-versions-of-gcc-and-g-on-ubuntu-20-04.htm)

According to the condition, the ‘if’ statement will return true if the practical marks are greater than 40. The theory marks are greater than or equal to 30, or if the sum of practical and theory marks is greater than or equal to 70.

Save the script to a file called and\_or\_operators.py with the following code.

```
# practical marks
practical_marks = float(input("Enter the practical marks: "))
# theory marks
theory_marks = float(input("Enter the theory marks: "))

# use AND and OR operator to Check if it passes the condition 
if (practical_marks &gt;= 40 and theory_marks &gt;= 30) or (practical_marks + theory_marks) &gt;=70:
  print("\nYou are successful")
else:
  print("\nYou are not successful")
```

The output appears as shown below:

![Usage of AND and OR operators in a conditional statement](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Usage-of-AND-and-OR-operators-in-a-conditional-statement.png?lossy=2&strip=1&webp=1)

Usage of AND and OR operators in a conditional statement

Accordingly, the if statement returns false for the input values 30 and 35. But true for the input values 40 and 45.

#### 10\. Switch case statement

Python does not have a switch-case statement like other programming languages, but a custom function may enforce it.

In the following script, the job\_details() function is generated to operate in the same way as the switch-case argument.

The feature has just one parameter and a switcher dictionary. Each index of the dictionary is tested for the value of the function parameter.

If a match is found, the function will return the index’s corresponding value; otherwise, the switcher’s second parameter value.get() method will be returned.

Save the script to a file called switch\_case\_statement.py with the following code.

```
# switch_case_statement.py

# Switcher for implementing switch case options
def job_details(ID):
switcher = {
"100": "Job Description: Software Engineer",
"200": "Job Description: Lawyer", 
"300": "Job Description: Graphics Designer",
}
'''The first argument will be returned if the match found and
nothing will be returned if no match found'''

return switcher.get(ID, "nothing")

# Take the job ID
job_id = input("Enter the job ID: ")
# Print the output
print(job_details(job_id))
```

If a match is made, the first argument will be returned; if no match is found, nothing will be returned – return the switcher.

Also Read

-   [Running JavaScript in the Linux Terminal](https://www.fosslinux.com/132860/running-javascript-in-the-linux-terminal.htm)
-   [Working with Numbers in Python](https://www.fosslinux.com/44077/working-with-numbers-in-python.htm)
-   [Basics of Working with the SQLite Database in Python](https://www.fosslinux.com/42798/basics-of-working-with-the-sqlite-databases-in-python.htm)

Accordingly, the script is run twice, and two job descriptions are printed based on the job id’s values as shown.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16058") })

![Switch case statement](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Switch-case-statement.png?lossy=2&strip=1&webp=1)

Switch case statement

#### 11\. While loop

The use of a while loop in Python is demonstrated using the following example.

The colon(:) is used to describe the loop’s starting block, and all loop statements must be indented properly; otherwise, an indentation error will occur.

The counter value is set to 1 in the following script, which is used in the loop. And the loop will iterate five times, printing the counter values after each iteration.

To enter the loop’s termination state, the counter value is incremented by one in each iteration.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16059") })

Save the script to a file called while\_loop.py with the following code.

```
# while_loop.py

# Initialize counter value
counter_val = 1
# Iterate the loop 10 times
while counter_val &lt; 11:
  # Print the counter value
  print ("counter value: %d" % counter_val)
  # Increment the counter_val
  counter_val = counter_val + 1
```

After running the script, the following output will appear.

![While loop](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/While-Loop.png?lossy=2&strip=1&webp=1)

While loop

#### 12\. For loop

Python’s for loop can be used for many purposes. A colon must define this loop’s starting block (:), and the statements must be defined by proper indentation.

A list of weekday names is specified in the following script. And a for loop is used to iterate and print each item on the list. The len() method is also used to count the total number of items in the list and to set the range() function’s limit.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16060") })

Save the script to a file called for\_loop.py with the following code.

Also Read

-   [Mastering the SQLite Database in Python](https://www.fosslinux.com/42799/mastering-the-sqlite-database-in-python.htm)
-   [10 Essential Python Run Command Usages You Need to Know](https://www.fosslinux.com/139347/essential-python-run-command-uses.htm)
-   [Customizing Vim: Advanced syntax highlighting techniques](https://www.fosslinux.com/134422/customizing-vim-advanced-syntax-highlighting-techniques.htm)

```
# Initialize the list
weekdays = ["Sunday", "Monday", "Tuesday","Wednesday", "Thursday","Friday", "Saturday"]
print("Seven Weekdays are:\n")
# Iterate the list using for loop
for day in range(len(weekdays)):
  print(weekdays[day])
```

After running the script, the following output will appear.

![For loop](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/For-loop.png?lossy=2&strip=1&webp=1)

For loop

#### 13\. Running a Python script from another Python script

It is often necessary to use a python file’s script from another python file. It’s easy to do, just like importing any module with the import keyword. String values initialize two variables in the holidays.py file.

This file is imported with the alias ‘h’ in the run\_python\_script\_from\_another\_script.py file. This is where you’ll find a list of month names.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16061") })

The flag variable is used to print the value of the holiday\_1 variable for October, November, and December only once.

The holiday\_2 variable’s value will be printed for the month of ‘April.’

When the else part of the if-else if-else declaration is executed, the other nine-month names will be printed.

run\_python\_script\_from\_another\_script.py is a Python script that allows you to use predefined values for the set holidays.

```
# Import another python script from holidays.py
import holidays as h

# month list
months = ["January", "February", "March", "April", "May", "June",
"July", "August", "September", "October", "November", "December"]

# Initial _flag variable to print holiday one time
_flag = 0

# Iterate the list using for loop
for m in months:
  if m == "October" or m == "November" or m == "December":
   if _flag == 0:
     print(" ### Now",h.holiday_1)
     _flag = 1
   elif m == "April":
    print(" ### Now",h.holiday_2)
   else:
    print("The current month is",m)
```

Save the second script to a file called holidays.py with the following code.

(adsbygoogle = window.adsbygoogle || \[\]).push({});

![](https://www.fosslinux.com//nc.pubpowerplatform.io/assets/pubpower-black-100x18.png)

(powerTag.Init = window.powerTag.Init || \[\]).push(function () { powerAPITag.display("pw\_16062") })

```
# holidays.py

# holiday values
holiday_1 = "Long holiday break"
holiday_2 = "Short holiday break"
```

If you run the script without any command-line arguments, you’ll get the following output, which shows the script filename.

![Running a Python script from another Python script](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Running-a-Python-script-from-another-Python-script.png?lossy=2&strip=1&webp=1)

Running a Python script from another Python script

#### 15\. Regular expressions

Regular expressions, also known as regex, are used in Python to fit or scan for and replace specific parts of a string based on a template.

Also Read

-   [How to install Python in Ubuntu and Linux Mint](https://www.fosslinux.com/1791/how-to-install-python-in-ubuntu-and-linux-mint.htm)
-   [Running JavaScript in the Linux Terminal](https://www.fosslinux.com/132860/running-javascript-in-the-linux-terminal.htm)
-   [How to install Visual Studio Code (VS Code) on Fedora](https://www.fosslinux.com/139864/how-to-install-visual-studio-code-vs-code-on-fedora.htm)

In Python, the ‘re’ module refers to the regular expression. The script below illustrates how to use regex in Python.

The pattern used in the script would fit strings that have a capital letter as the first character. In fact, the pattern will be matched with a string value using the match() process.

A success message will be printed if the method returns true; otherwise, an instructional message will be printed.

Save the script to a file called regular\_expressions.py with the following code.

```
# regular_expressions.py

# Import re module
import re

# Take any string data
string_data = input("input a string : ")

# search pattern
search_pattern = '^[A-Z]'

# match the pattern with input value
_found = re.match(search_pattern, string_data)

# message printed is based on the return value

if _found:
  print("value starts with a capital letter")
else:
  print("Re-enter starting with a capital letter")
```

After running the script, the following output will appear.

![Regular expressions](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Regular-expressions.png?lossy=2&strip=1&webp=1)

Regular expressions

#### 16\. Usage of getpass

getpass is a useful Python module for receiving password feedback from the user. The getpass module is illustrated in the following script below.

The getpass() method is used to take the input and convert it to a password. Besides, the if statement is used to compare the input value to the given password.

If the password matches, the message “you are authenticated” will appear; otherwise, the message “you are not authenticated” will appear.

Save the script to a file called get\_pass.py with the following code.

```
# get_pass.py

# import getpass module
import getpass

# request user to input a password
passwd = getpass.getpass('Password:')

# validate the password entered by the user against the given password
if passwd == "password":
  print("authentication successful")
else:
  print("authentication failed ")
```

When the script is run from the terminal, the input value is not shown for other Linux passwords.

Also Read

-   [Logging in Python – Your One Stop Guide](https://www.fosslinux.com/43772/logging-in-python-your-one-stop-guide.htm)
-   [How to Update and Manage Python Versions on Linux](https://www.fosslinux.com/143798/how-to-update-and-manage-python-versions-on-linux.htm)
-   [Getting Started with Python](https://www.fosslinux.com/43945/getting-started-with-python.htm)

The script is run twice from the terminal. Once with an invalid password and once with a correct password, as shown in the diagram below.

![Usage of getpass](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Usage-of-getpass.png?lossy=2&strip=1&webp=1)

Usage of getpass

#### 17\. Date format

The date value in Python can be formatted in many ways. The datetime module is used in the following script to set the existing and custom date values.

The current device date and time are read using the today() function. The formatted date value is then printed using the date object’s various property names.

The next section of the script demonstrates how to allocate and print a custom date value.

Save the script to a file called date\_format.py with the following code.

```
# date_format.py

# program to format and print date using the library datetime

from datetime import date

# capture the date today
date_today = date.today()

# Print the formatted date
print("The date today is :%d-%d-%d" % (date_today.day,date_today.month,date_today.year))

# customize the given date
custom_date = date(2021, 4, 5)
print("The custom date is:",custom_date)
```

After running the script, the following output will appear.

![Date format](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Date-format.png?lossy=2&strip=1&webp=1)

Date format

#### 18\. Adding and deleting objects from a list

Python’s list object is used to solve many problems. To work with the list object, Python has several built-in functions.

The following example demonstrates how to add and delete new items from a list. The script declares a list of four objects.

-   The Insert() method is used to add a new item to the list’s second location.
-   The remove() method is used to find and remove a specific item from a list.

Following the insertion and deletion, the list is written.

Save the script to a file called list\_methods.py with the following code.

Also Read

-   [What Causes ‘Segmentation Fault’ in Linux? How to Fix It](https://www.fosslinux.com/142468/what-causes-segmentation-fault-in-linux-how-to-fix-it.htm)
-   [How to install Visual Studio Code (VS Code) on Fedora](https://www.fosslinux.com/139864/how-to-install-visual-studio-code-vs-code-on-fedora.htm)
-   [A complete guide to writing comments in YAML](https://www.fosslinux.com/134420/a-complete-guide-to-writing-comments-in-yaml.htm)

```
# list_methods.py

# Declare a list of sports
sports = ["soccer","rugby","netball","volleyball"]

# Insert a new sport in the 3rd position
sports.insert(2, "table tennis")

# Resultant list after inserting
print("The sports list after insert:")
print(sports)

# Remove sport
sports.remove("netball")

# Print the sports list after delete
print("The sports list after delete:")
print(sports)
```

After running the script, the following output will appear.

![Adding and deleting objects from a list](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Adding-and-deleting-objects-from-a-list.png?lossy=2&strip=1&webp=1)

Adding and deleting objects from a list

#### 19\. List comprehension

List comprehension is a Python function that allows you to build a new list from any string, tuple, or another list.

The for loop and lambda function can be used to accomplish the same mission.

The script below demonstrates two separate applications of list comprehension – List comprehension is used to translate a string value into a list of characters.

A tuple is then translated to a list in the same manner.

Save the script to a file called list\_comprehension.py with the following code.

```
# list_comprehension.py

# list of characters creation using list comprehension
build_char_list = [ char for char in "comprehension" ]
print(build_char_list)

# Define a tuple of multi-million companies
companies_tuple = ("Facebook","Google", "Twitter", "IBM","Apple", "HP", "DELL")

# use list comprehension to create a list from tuple 
companies_list = [ site for site in companies_tuple ]
print(companies_list)
```

After running the script, the following output will appear below.

![List comprehension](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/List-comprehension.png?lossy=2&strip=1&webp=1)

List comprehension

20\. Slice data

The slice() method in Python is used to cut a specific portion of a string. There are three parameters in this system – Start, stop, and phase is the three parameters.

The stop parameter is needed, while the other two parameters are optional. The slice() method is demonstrated with one, two, and three parameters in the following script. When only one parameter is defined in the slice() process, the required parameter stop is used.

Also Read

-   [PyCharm for Linux Users: A Comprehensive Python IDE Guide](https://www.fosslinux.com/136794/pycharm-for-linux-users-a-comprehensive-python-ide-guide.htm)
-   [How to install Python Anaconda on Linux](https://www.fosslinux.com/42614/how-to-install-python-anaconda-on-linux.htm)
-   [A complete guide to writing comments in YAML](https://www.fosslinux.com/134420/a-complete-guide-to-writing-comments-in-yaml.htm)

The start and stop parameters are used when the two parameters are used in the slice() process. Finally, start, end, and phase parameters are used when all three parameters are used.

Save the script to a file called slice\_data.py with the following code.

```
# slice_data.py

# string value assignment
_text = "slicing data details"

# use one parameter to Slice
slice_obj = slice(5)
print("one parameters: ",_text[slice_obj])

# use two parameters to Slice
slice_obj = slice(6,12)
print("two parameters: ",_text[slice_obj])

# use three parameters to Slice
slice_obj = slice(6,25,5)
print("three parameters: ", _text[slice_obj])
```

After running the script, the following output will appear. The argument value for the first slice() method is 5. It sliced the five text variables that are printed as output into five characters. Arguments 6 and 12 are used in the second slice() form. The slicing process begins at position six and ends after 12 characters.

![Slice Data](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Slice-Data.png?lossy=2&strip=1&webp=1)

Slice Data

The third slice() method takes three arguments: 6, 25, and 5. The slicing starts at position six and ends after 25 characters, with each move omitting five characters.

#### 21\. Add and search data in the dictionary

Like the associative array in other programming languages, the dictionary object is used in Python to store multiple data.

The following script demonstrates how to add a new item to the dictionary and scan for any item.

The script declares a dictionary of customer knowledge, with the index containing the sports ID and the meaning containing the sports name. After that, a new sports record is added to the dictionary’s end. To check the dictionary, a sports ID is used as input.

To iterate the dictionary’s indexes and check the dictionary’s input value, a for loop and an if condition is used.

Save the script to a file called add\_search\_data.py with the following code.

```
# add_search_data.py

# Define a dictionary
sports = {'100':'soccer','200':'rugby',
'300':'table tennis','400':'volleyball', '500':'Basketball'}

# Append a new data
sports['600'] = 'netball'

print("The sports names are:")
# Print the values of the dictionary
for sport in sports:
  print(sports[sport])

# Take sport ID as input to search
sport_name = input("Enter Sport ID:")

# Search the sport ID in the dictionary
for sport in sports:
  if sport == sport_name:
    print(sports[sport])
break


```

After running the script and selecting ‘3’,’400′ as the sport ID value, the following output will appear as:

![Add and search data in the dictionary](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Add-and-search-data-in-the-dictionary.png?lossy=2&strip=1&webp=1)

Add and search data in the dictionary

#### 22\. Add and search data in a Python set

The script below demonstrates how to add and search data in a Python set. The script declares a set of integer data. To add new data to the package, use the add() method.

In a for loop and if condition, an integer value will be used to check for a set value.

Save the script to a file called add\_search\_data\_in\_python.py with the following code.

```
# add_search_data_in_python.py

# number set definition
number_set = {23, 90, 56, 78, 12, 34, 67}

# new data is added

number_set.add(50)

# set values printing
print(number_set)

_message = "that number is not available."

# request use for a number value for search
search_val = int(input("input a number:"))
# Search the number in the set
for val in number_set:
  if val == search_val:
   _message = "that number is available."
break

print(_message)
```

The script is run twice, once with the integer value 46 and once with 90. Herein, the number 46 isn’t found in the set, so “that number is not available.” is printed. However, the number 90 is found in the set, and the message “that number is available.” is printed.

The output of the above script appears as shown in the diagram below.

![Add and search data in a Python set](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Add-and-search-data-in-a-Python-set.png?lossy=2&strip=1&webp=1)

Add and search data in a Python set

#### 23\. Count the number of items on the list

The count() method in Python is used to count how many times a string occurs in another string.

There are three possible claims. The first argument is needed, and it searches for a specific string within a larger string. The method’s other two arguments are used to restrict the search by specifying the search positions.

The count() method is used with one argument in the following script to measure the word “Python” in the string variable.

Save the script to a file called count\_items\_list.py with the following code.

```
# count_items_list.py

# string definition
string = 'Python learning apart from Java, Python, Kotlin PHP, Python &amp; PERL'

# search string
search = 'Python'

# count value stored
count = string.count(search)

# formatted output Printed
print("%s appears %d times" % (search, count))
```

After running the script, the following output will appear.

![Count the number of items on the list](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Count-the-number-of-items-on-the-list.png?lossy=2&strip=1&webp=1)

Count the number of items on the list

#### 24\. Create a function and call it

The following script illustrates how to declare and call user-defined functions in Python.

Two functions are declared here. First, to measure the sum of two numbers and print the result, use the addition() function with two arguments.

Secondly, the area() function takes only one argument and calculates a circle area before returning the caller’s result through the return statement.

Save the script to a file called create\_a\_function\_and\_call\_it.py with the following code.

```
# create_a_function_and_call_it.py

# Define addition function
def add(first_number, second_number):
_result = first_number + second_number
return _result

# use return statement to define area function 
def area(_radius):
_result = 3.14 * _radius * _radius
return _result

# add function called
print("Addition results: ",add(400, 300))


# area function called
print("Circle's Area: ",area(4))
```

After running the script, the following output will appear.

![Create a function and call it](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Create-a-function-and-call-it.png?lossy=2&strip=1&webp=1)

Create a function and call it

#### 25\. Throw and catch the exception

To throw and catch the exception, try and catch blocks are used.

In Python, the try-catch block is shown in the following script. The try block takes a number value as input and checks if it is even or odd.

If any non-numeric value is given as input, a ValueError is thrown, and an exception is thrown to the catch block, which prints the error message.

Save the script to a file called try\_block.py with the following code.

```
# try_block.py

# The Try block
try:
# request user to input a number
num_val = int(input("Input a number: "))
if num_val % 2 == 0:
  print("Even Number")
else:
  print("Odd Number")

# The Exception block 
except (ValueError):
  # error message printed
  print("Input a numeric value")
```

After running the script, the following output will appear.

![Throw and catch the exception](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Throw-and-catch-the-exception.png?lossy=2&strip=1&webp=1)

Throw and catch the exception

26\. Read and Write file

The script below demonstrates how to read and write to a file in Python. The vector filename contains the filename.

The file is opened for writing at the start of the script with the open() process. And the write() method is used to write three lines to the register.

Following that, the open() method is used to open the same file for reading. And the for loop is used to read and print of line of the file.

Save the script to a file called read\_write\_file.py with the following code.

```
filename = "cities.txt"

# Open file for writing
fileHandler = open(filename, "w")

# add cities
fileHandler.write("New York\n")
fileHandler.write("Washington\n")
fileHandler.write("Los Angeles\n")

# Close the file
fileHandler.close()

# Open file for reading
lines = open(filename, "r")

# Reading a file line by line
for line in lines:
print(line)

# Close the file
fileHandler.close()
```

After running the script, the following output will appear.

![Read and Write file](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Read-and-Write-file.png?lossy=2&strip=1&webp=1)

Read and Write file

#### 27\. List files in a directory

The os module of Python can be used to read the contents of any directory.

The following script demonstrates how to use the os module in Python to get a list of files in a given directory.

The script uses the listdir() method to get a list of files and directories in a directory. Further, the directory content is printed using a for a loop.

Save the script to a file called list\_files\_in\_directory.py with the following code.

Also Read

-   [How to install Python Anaconda on Linux](https://www.fosslinux.com/42614/how-to-install-python-anaconda-on-linux.htm)
-   [How to install and use WebStorm on Ubuntu](https://www.fosslinux.com/122888/how-to-install-and-use-webstorm-on-ubuntu.htm)
-   [How to install Node.js and NPM packages on Ubuntu](https://www.fosslinux.com/26264/how-to-install-node-js-and-npm-packages-on-ubuntu.htm)

```
# list_files_in_directory.py

# to read directory, the Import os module
import os

# directory path 
_path = '/home/tuts/Documents'

# Reading file content's
_files = os.listdir(_path)

# Print directory's content

for _file in _files:
  print(_file)
```

If the directory’s specified path exists, the directory’s content will appear after running the script.

![List files in a directory](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/List-files-in-a-directory.png?lossy=2&strip=1&webp=1)

List files in a directory

#### 28\. Read and write data with Pickle

The following script demonstrates how to write and read data with Python’s Pickle module.

An object is declared and initialized with five numeric values in the script. Besides, the dump() method is used to save the data of this object to a disk. The data is then read from the same file and stored in an array using the load() process.

Save the script to a file called read\_write\_data\_with\_pickle.py with the following code.

```
# read_write_data_with_pickle.py

# Import pickle module
import pickle as p

# object to store data is declared
data_object = []

# Iterate the for loop for 10 times
for val in range(10,20):
data_object.append(val)

# file for writing data is opened
file_handler = open('languages', 'wb')

# Dump the object's data into the file
p.dump(data_object, file_handler)

# close the file handler
file_handler.close()

# Open a file for reading the file
_handler = open('languages', 'rb')
# Load the data from the file after deserialization
data_object = p.load(_handler)
# Iterate the loop to print the data
for v in data_object:
print('Data Value : ', v)
# close the file handler
_handler.close()
```

After running the script, the following output will appear.

![Read and write data with Pickle](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Read-and-write-data-with-Pickle.png?lossy=2&strip=1&webp=1)

Read and write data with Pickle

29\. Define a class and method

The following script demonstrates how to declare and access a class and method in Python.

A class is described here, along with a class variable and a process. Subsequently, the class variable and class method are then accessed by declaring a class object.

Save the script to a file called class\_method.py with the following code.

```
# class_method.py

# class definition
class Job:
  name = "Software Engineer"

  # Define the method
  def job_details(self):
    print("place: New York")
    print("Department: IT")
    print("Salary: $100,000")

# Create the Job object 
_job = Job()

# the class variable is Printed
print("Name:",_job.name)

# trigger the class method
_job.job_details()
```

After running the script, the following output will appear.

![Define a class and method](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Define-a-class-and-method.png?lossy=2&strip=1&webp=1)

Define a class and method

#### 30\. Range function usage

The following script demonstrates how to use the range function in Python.

Three arguments can be passed to this function – start, stop, and stage. However, the stop claim must be used.

The default value of the start is 0 when just one argument is used. range() functions of one, two, and three arguments are used in the three for loops.

Save the script to a file called range\_function.py with the following code.

```
# range_function.py

print('The function range() with one parameter\n')

for _range in range(8):
  print(_range, end=' ')

print('\nThe function range() with two parameter\n')
for _range in range(8,20):
  print(_range, end=' ')


print('\nThe function range() with three parameter\n')
for _range in range(8,20,2):
  print(_range, end=' ')

print('\n')
```

After running the script, the following output will appear.

![Range function usage](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Range-function-usage.png?lossy=2&strip=1&webp=1)

Range function usage

#### 31\. The map() function

The map() function in Python is used to create a list from any user-defined function and any iterable object.  
The power\_fun() function is specified in the following script to calculate the xn, and it is used in the first argument of the map() function.

The second argument of the map() function is a list called numbers.

The user’s x value will be taken, and the map() function will return a list of x power values based on the numbers list’s item values.

Save the script to a file called map\_function.py with the following code.

```
# map_function.py

# power function definition &amp; calculation
def power_fun(n): 
  return x ** n

# request user to input the value of x
x = int(input("Enter the value of x:"))

# Define a tuple that will store numbers
num_val = [2, 3, 4]

# use map() to calculate the x to the power n 
map_result = map(power_fun, num_val)
print(list(map_result))
```

After running the script, the following output will appear.

![The map() function](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/The-map-function.png?lossy=2&strip=1&webp=1)

The map() function

#### 32\. Filtering data from an iterable object with the filter() feature

The filter() function in Python uses a custom function to filter data from an iterable object and generate a list of objects for which the function returns.

The SelectedSport() function is used in the following script to construct a list of filtered data based on the selectedList objects.

Save the script to a file called filter\_function.py with the following code.

```
# filter_function.py

# Define a list of all sports
all_sports= ['soccer', 'basketball', 'volleyball', 'netball', 'athletics']

# Define the function to filters selected sports
def SelectedSport(val):
  selected_sports = ['athletics', 'soccer','rugby']
  if(val in selected_sports):
    return True
  selectedList = filter(SelectedSport, all_sports)
  print('The selected sports are:')
  for item in selectedList:
    print(item)
```

After running the script, the following output will appear.

![Filtering data from an iterable object with the filter() feature](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Filtering-data-from-an-iterable-object-with-the-filter-feature.png?lossy=2&strip=1&webp=1)

Filtering data from an iterable object with the filter() feature

#### 33\. Script to check External IP Address

Needing to know your external IP address isn’t something that happens all the time…until it does. Here’s an example Python script that illustrates how quick it is to use Python for these otherwise time-consuming tasks.  
This is a basic Python script for determining your external IP address. The requests and re-modules are first imported.

Save the script to a file called check\_external\_ip.py with the following code.

```
# check_external_ip.py

# script to check your external IP address
import re
import requests

ur_url = "http://checkip.dyndns.org"
request = requests.get(ur_url)
_result = request.text.split(': ', 1)[1]
your_ip = _result.split('&lt;/body&gt;&lt;/html&gt;', 1)[0]

print(your_ip)
```

![Script to check External IP Address](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Script-to-check-External-IP-Address.png?lossy=2&strip=1&webp=1)

Script to check External IP Address

#### 34\. roll the dice

This is a traditional “roll the dice” game. Since we want to randomize the numbers we get from the dice, we’ll use the random module.

The lowest and highest number of dice are set as variables (min and max). After that, we use a while loop to allow the user to roll the dice once more.

The roll again parameter can be set to any value; in this case, it’s set to “yes” or “y,” but you can also add other values.

Save the script to a file called roll\_dice.py with the following code.

Also Read

-   [Python: Check file existence with built-in functions](https://www.fosslinux.com/139195/python-check-file-existence-with-built-in-functions.htm)
-   [Working with Numbers in Python](https://www.fosslinux.com/44077/working-with-numbers-in-python.htm)
-   [Pip installation across Linux distros: A detailed guide](https://www.fosslinux.com/136561/pip-installation-across-linux-distros-a-detailed-guide.htm)

```
# roll_dice.py

import random

def roll_dice(min_val, max_val):
  while True:
    print("Dice Rolling...")
    print(f"Your number is {random.randint(min_val, max_val)}")
    result = input("Do you want to roll the dices again? (y/n) ")
    if result.lower() == "n":
      break

roll_dice(1, 6)
```

After running the above script, the following output will appear.

![roll the dice](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/roll-the-dice.png?lossy=2&strip=1&webp=1)

roll the dice

#### 35\. Searching your PC for specific files

we’ll explain how to walk a directory tree with the os.walk() module function and match filenames with the fnmatch module. Also, we’ll teach you how to use the os.walk() module function to walk a directory tree and the fnmatch module to match file names in this article.

##### What exactly is OS.walk?

It walks the tree top-down or bottom-up to create file names in a directory tree. It returns a 3-tuple for each directory in the tree rooted at directory top, including top itself, i.e., dirpath, dirnames, filenames.

-   dirpath # is a string that represents the directory’s path.
-   dirnames # is a list of the subdirectories’ names in dirpath that do not begin with the letters ‘.’ or ‘..’.
-   filenames # is a list of non-directory files’ names in dirpath. The names in the lists do not include any path components.

Do os.path.join to get a complete path beginning with top to a file or directory in dirpath (dirpath, name). For wild-card pattern matching, the fnmatch module is used.

##### Matching is easy

fnmatch() compares a single file name to a pattern and returns a boolean that indicates whether they match or not. If the operating system uses a case-sensitive file system, the comparison is case-sensitive.

The fnmatch module compares file names to glob-style patterns that Unix shells use. These are not to be confused with the more complex normal expression laws. It’s nothing more than a string matching process.

If you choose to use a different pattern type, such as regular expressions, simply fit your filenames with regex operations. This script searches the hard drive for all image files using the commands’ os.walk’ and ‘fnmatch’ with filters.

Save the script to a file called searching\_specific\_files.py with the following code.

```
# searching_specific_files.py

import fnmatch
import os

root_path = '/home/tuts/Documents'
_pattern = '*.mp4'

for _root, dirs, _files in os.walk(root_path):
for _file in fnmatch.filter(_files, _pattern):
print( os.path.join(_root, _file))
```

![Searching your PC for specific files](https://b1490832.smushcdn.com/1490832/wp-content/uploads/2021/03/Searching-your-PC-for-specific-files.png?lossy=2&strip=1&webp=1)

Searching your PC for specific files
