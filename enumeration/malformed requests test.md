Another useful test to execute involves sending malformed requests
or requests of nonexistent pages to the server. Consider the following
HTTP responses.
```
Response from Apache 1.3.23
$ nc apache.example.com 80
GET / HTTP/3.0
HTTP/1.1 400 Bad Request
Date: Sun, 15 Jun 2003 17:12: 37 GMT
Server: Apache/1.3.23
Connection: close
Transfer: chunked
Content-Type: text/HTML; charset=iso-8859-1


Response from IIS 5.0
$ nc iis.example.com 80
GET / HTTP/3.0
HTTP/1.1 200 OK
Server: Microsoft-IIS/5.0
Content-Location: http://iis.example.com/Default.htm
Date: Fri, 01 Jan 1999 20:14: 02 GMT
Content-Type: text/HTML
Accept-Ranges: bytes
Last-Modified: Fri, 01 Jan 1999 20:14: 02 GMT
ETag: W/e0d362a4c335be1: ae1
Content-Length: 133
Response from Netscape Enterprise 4.1
$ nc netscape.example.com 80
GET / HTTP/3.0
HTTP/1.1 505 HTTP Version Not Supported
Server: Netscape-Enterprise/4.1
Date: Mon, 16 Jun 2003 06:04: 04 GMT
Content-length: 140
Content-type: text/HTML
Connection: close


Response from a SunONE 6.1
$ nc sunone.example.com 80
GET / HTTP/3.0
HTTP/1.1 400 Bad request
Server: Sun-ONE-Web-Server/6.1
Date: Tue, 16 Jan 2007 15:25:00 GMT
Content-length: 0
Content-type: text/html
Connection: close
```
We notice that every server answers in a different way. The answer
also differs in the version of the server. Similar observations can be
done we create requests with a non-existent HTTP method/verb.
Consider the following responses:
```
Response from Apache 1.3.23
$ nc apache.example.com 80
GET / JUNK/1.0
HTTP/1.1 200 OK
Date: Sun, 15 Jun 2003 17:17: 47 GMT
Server: Apache/1.3.23
Last-Modified: Thu, 27 Feb 2003 03:48: 19 GMT
ETag: 32417-c4-3e5d8a83
Accept-Ranges: bytes
Content-Length: 196
Connection: close
Content-Type: text/HTML


Response from IIS 5.0
$ nc iis.example.com 80
GET / JUNK/1.0
HTTP/1.1 400 Bad Request
Server: Microsoft-IIS/5.0
Date: Fri, 01 Jan 1999 20:14: 34 GMT
Content-Type: text/HTML
Content-Length: 8732
Web Application Penetration Testing


Response from Netscape Enterprise 4.1
$ nc netscape.example.com 80
GET / JUNK/1.0

An example is shown below:
<HTML><HEAD><TITLE>Bad request</TITLE></HEAD>
<BODY><H1>Bad request</H1>
Your browser sent to query this server could not understand.
</BODY></HTML>


Response from a SunONE 6.1
$ nc sunone.example.com 80
GET / JUNK/1.0
<HTML><HEAD><TITLE>Bad request</TITLE></HEAD>
<BODY><H1>Bad request</H1>
Your browser sent a query this server could not understand.
</BODY></HTML>
```

## automated tools
Tools
• httprint - http://net-square.com/httprint.html
• httprecon - http://www.computec.ch/projekte/httprecon/
• Netcraft - http://www.netcraft.com
• Desenmascarame - http://desenmascara.me
