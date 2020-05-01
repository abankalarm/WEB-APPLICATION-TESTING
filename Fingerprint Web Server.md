Web server fingerprinting is a critical task for the penetration tester.
Knowing the version and type of a running web server allows testers
to determine known vulnerabilities and the appropriate exploits to use
during testing.
```
Response from Apache 1.3.23
$ nc apache.example.com 80
HEAD / HTTP/1.0
HTTP/1.1 200 OK
Date: Sun, 15 Jun 2003 17:10: 49 GMT
Server: Apache/1.3.23
Last-Modified: Thu, 27 Feb 2003 03:48: 19 GMT
ETag: 32417-c4-3e5d8a83
Accept-Ranges: bytes
Content-Length: 196
Connection: close
Content-Type: text/HTML


Response from IIS 5.0
$ nc iis.example.com 80
HEAD / HTTP/1.0
HTTP/1.1 200 OK
Server: Microsoft-IIS/5.0
Content-Location: http://iis.example.com/Default.htm
Date: Fri, 01 Jan 1999 20:13: 52 GMT
Content-Type: text/HTML
Accept-Ranges: bytes
Last-Modified: Fri, 01 Jan 1999 20:13: 52 GMT
ETag: W/e0d362a4c335be1: ae1
Content-Length: 133


Response from Netscape Enterprise 4.1
$ nc netscape.example.com 80
HEAD / HTTP/1.0
HTTP/1.1 200 OK
Server: Netscape-Enterprise/4.1
Date: Mon, 16 Jun 2003 06:01: 40 GMT
Content-type: text/HTML
Last-modified: Wed, 31 Jul 2002 15:37: 56 GMT
Content-length: 57
Accept-ranges: bytes
Connection: close31
Web Application Penetration Testing


Response from a SunONE 6.1
$ nc sunone.example.com 80
HEAD / HTTP/1.0
HTTP/1.1 200 OK
Server: Sun-ONE-Web-Server/6.1
Date: Tue, 16 Jan 2007 15:23:37 GMT
Content-length: 0
Content-type: text/html
Date: Tue, 16 Jan 2007 15:20:26 GMT
Last-Modified: Wed, 10 Jan 2007 09:58:26 GMT
Connection: close
```
We can notice that the ordering of the Date field and the Server field
differs between Apache, Netscape Enterprise, and IIS.
