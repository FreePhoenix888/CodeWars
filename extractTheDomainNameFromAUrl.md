## CodeWars Extract the domain name from a URL

![code wars badge](https://www.codewars.com/users/FreePhoenix/badges/large)

#### [KATA](https://www.codewars.com/kata/extract-the-domain-name-from-a-url-1)

### Description:

Write a function that when given a URL as a string, parses out just the domain name and returns it as a string.

### Example:

domainName("http://github.com/carbonfive/raygun") == "github"
domainName("http://www.zombie-bites.com") == "zombie-bites"
domainName("https://www.cnet.com") == "cnet"

## 1 Solution:

    function domainName(url) {
    	let regex = new RegExp(/(?:https?:\/\/)?(?:www\.)?(.*?)(\..*)+/);
    	return url.match(regex)[1];
    }

## 2 Solution:

    function domainName(url){
    	url = url.replace("https://", '');
    	url = url.replace("http://", '');
    	url = url.replace("www.", '');
    	return url.split('.')[0];
    };
