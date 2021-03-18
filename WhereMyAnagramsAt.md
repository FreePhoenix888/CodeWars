## CodeWars Where my anagrams at?

![code wars badge](https://www.codewars.com/users/FreePhoenix/badges/large)

#### [KATA](https://www.codewars.com/kata/where-my-anagrams-at)

### Description:

What is an anagram? Well, two words are anagrams of each other if they both contain the same letters. For example:

    'abba' & 'baab' == true

    'abba' & 'bbaa' == true

    'abba' & 'abbba' == false

    'abba' & 'abca' == false

### Example:

    anagrams('abba', ['aabb', 'abcd', 'bbaa', 'dada']) => ['aabb', 'bbaa']

    anagrams('racer', ['crazer', 'carer', 'racar', 'caers', 'racer']) => ['carer', 'racer']

    anagrams('laser', ['lazing', 'lazy', 'lacer']) => []

## 1 Solution:

    String.prototype.sort = function() {
    return this.split("").sort().join("");
    };

    function anagrams(word, words) {
    return words.filter(function(x) {
    		return x.sort() === word.sort();
    });
    }
