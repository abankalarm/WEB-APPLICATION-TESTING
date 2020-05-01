## robots.txt

The User-Agent directive refers to the specific web spider/robot/
crawler. .
For example the ```User-Agent: Googlebot``` refers to the spider
from Google while ```“User-Agent: bingbot”[1] ```refers to crawler from
Microsoft/Yahoo!. User-Agent: * in the example above applies to all
web spiders/robots/crawlers [2] as quoted below:

The Disallow directive specifies which resources are prohibited by
spiders/robots/crawlers. In the example above, directories such as
the following are prohibited:
```
...
Disallow: /search
Disallow: /sdch
Disallow: /groups
Disallow: /images
Disallow: /catalogs
...
```
Web spiders/robots/crawlers can intentionally ignore the Disallow
directives specified in a robots.txt file [3], such as those from So-
cial Networks[2] to ensure that shared linked are still valid.

### robots.txt in webroot - with “wget” or “curl”
eg curl -O http://www.google.com/robots.txt

## Meta tag
<META> tags are located within the HEAD section of each HTML Doc-
ument and should be consistent across a web site in the likely event
that the robot/spider/crawler start point does not begin from a docu-
ment link other than webroot i.e. a “deep link”[5].
If there is no “<META NAME=”ROBOTS” ... >” entry then the “Robots
Exclusion Protocol” defaults to “INDEX,FOLLOW” respectively. There-
fore, the other two valid entries defined by the “Robots Exclusion Pro-
tocol” are prefixed with “NO...” i.e. “NOINDEX” and “NOFOLLOW”.
Web spiders/robots/crawlers can intentionally ignore the “<META
NAME=”ROBOTS”” tag as the robots.txt file convention is preferred.
Hence, <META> Tags should not be considered the pimary mecha-
nism, rather a complementary control to robots.txt.
  
  
