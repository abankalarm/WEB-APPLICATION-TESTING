## How to Test

### Blackbox testing
Web application discovery is a process aimed at identifying web ap-
plications on a given infrastructure. The latter is usually specified as
a set of IP addresses (maybe a net block), but may consist of a set of
DNS symbolic names or a mix of the two.

`1. Different base URL
The obvious entry point for a web application is www.example.
com, i.e., with this shorthand notation we think of the web applica-
tion originating at http://www.example.com/ (the same applies for
https). However, even though this is the most common situation,
there is nothing forcing the application to start at “/”.
For example, the same symbolic name may be associated to three
web applications such as: http://www.example.com/url1 http://
www.example.com/url2 http://www.example.com/url3
In this case, the URL http://www.example.com/ would not be as-
sociated with a meaningful page, and the three applications would
be “hidden”, unless the tester explicitly knows how to reach them,
i.e., the tester knows url1, url2 or url3. There is usually no need to
publish web applications in this way, unless the owner doesn’t want
them to be accessible in a standard way, and is prepared to inform
the users about their exact location.

2.Non-standard ports
While web applications usually live on port 80 (http) and 443 (https),
there is nothing magic about these port numbers. In fact, web ap-
plications may be associated with arbitrary TCP ports, and can be
referenced by specifying the port number as follows: http[s]://www.
example.com:port/.

nmap –PN –sT –sV –p0-65535 192.168.1.100

3. Virtual hosts
DNS allows a single IP address to be associated with one or more
symbolic names. For example, the IP address 192.168.1.100 might
be associated to DNS names www.example.com, helpdesk.example.
com, webmail.example.com. It is not necessary that all the names
belong to the same DNS domain. This 1-to-N relationship may be re-
flected to serve different content by using so called virtual hosts. The
information specifying the virtual host we are referring to is embed-
ded in the HTTP 1.1 Host: header [1].
One would not suspect the existence of other web applications in ad-
dition to the obvious www.example.com, unless they know of help-
desk.example.com and webmail.example.com.

DNS zone transfers
This technique has limited use nowadays, given the fact that zone
transfers are largely not honored by DNS servers. However, it may
be worth a try. First of all, testers must determine the name servers
serving x.y.z.t. If a symbolic name is known for x.y.z.t (let it be www.
example.com), its name servers can be determined by means of tools
such as nslookup, host, or dig, by requesting DNS NS records.
If no symbolic names are known for x.y.z.t, but the target definition
contains at least a symbolic name, testers may try to apply the same
process and query the name server of that name (hoping that x.y.z.t
will be served as well by that name server). For example, if the target
consists of the IP address x.y.z.t and the name mail.example.com, de-
termine the name servers for domain example.com.

Webhosting info: http://whois.webhosting.info/ syntax: http://
whois.webhosting.info/x.x.x.x

DNSstuff: http://www.dnsstuff.com/ (multiple services available)

tomDNS: http://www.tomdns.net/index.php (some services are still
private at the time of writing)

SEOlogs.com: http://www.seologs.com/ip-domains.html (re-
verse-IP/domain lookup)

DNS lookup tools such as nslookup, dig and similar. and nikto
