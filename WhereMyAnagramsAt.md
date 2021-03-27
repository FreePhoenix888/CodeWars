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
    
    
# JS

## 1 Solution:

    String.prototype.sort = function() {
    return this.split("").sort().join("");
    };

    function anagrams(word, words) {
    return words.filter(function(x) {
    		return x.sort() === word.sort();
    });
    }
    
    
## 2 Solution:

    function anagrams(word, words) {
    	let result = [];
    	for (let i = 0; i < words.length; i++) {
    		// Checks if lengths are not equal
    		if (word.length != words[i].length) {
    			continue;
    		}

    		// Sorts word and words to compare. adad = aadd
    		let sortedWord = [...word].sort();
    		let sortedWordToCompare = [...words[i]].sort();

    		// Compare arrays of letters
    		for (let j = 0; j < word.length; j++) {
    			if (sortedWord[j] != sortedWordToCompare[j]) {
    				break;
    			}

    			if (j == word.length - 1) {
    				result.push(words[i]);
    			}
    		}
    	}
    	return result;
    }


# C#
    using System;
    using System.Collections.Generic;
    using System.Linq;

    public static class Kata
    {
        public static List<string> Anagrams(string word, List<string> words)
        {
            List<string> result = new List<string>(words.Count());

            char[] wordLetters = word.ToLower().ToCharArray();
            Array.Sort(wordLetters);

            foreach (string wordFromList in words)
            {
                char[] wordFromListLetters = wordFromList.ToLower().ToCharArray();
                Array.Sort(wordFromListLetters);

                if(Enumerable.SequenceEqual(wordLetters, wordFromListLetters))
                {
                    result.Add(wordFromList);
                }
            }

            return result;
            throw new NotImplementedException();
        }
    }
