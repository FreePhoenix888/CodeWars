## CodeWars Pete, the baker!

![code wars badge](https://www.codewars.com/users/FreePhoenix/badges/large)

#### [KATA](https://www.codewars.com/kata/the-hashtag-generator/javascript)

### Description:

The marketing team is spending way too much time typing in hashtags.
Let's help them with our own Hashtag Generator!

Here's the deal:

It must start with a hashtag (#).
All words must have their first letter capitalized.
If the final result is longer than 140 chars it must return false.
If the input or the result is an empty string it must return false.

### Example:

" Hello there thanks for trying my Kata" => "#HelloThereThanksForTryingMyKata"
" Hello World " => "#HelloWorld"
"" => false

## 1 Solution:

    function generateHashtag(str) {
    	return str.length > 140 || str === ""
    		? false
    		: "#" + str.split(" ").map(capitalize).join("");
    }

    function capitalize(str) {
    	return str.charAt(0).toUpperCase() + str.slice(1);
    }

## 2 Solution:

    function generateHashtag(str) {
    	if (str.trim() == ``) return false;
    	let modifiedStr = str
    		.split(` `)
    		.map((word) => word.charAt(0).toUpperCase() + word.slice(1))
    		.join(``);
    	let strWithHashtag = `#${modifiedStr}`;
    	if (strWithHashtag.length > 140) return false;
    	return strWithHashtag;
    }
