## CodeWars #14 Playing with digits!

![code wars badge](https://www.codewars.com/users/FreePhoenix/badges/large)

#### [KATA](https://www.codewars.com/kata/55c45be3b2079eccff00010f)

### Description:

Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.

Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).

If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.

### Example:

"is2 Thi1s T4est 3a" --> "Thi1s is2 3a T4est"
"4of Fo1r pe6ople g3ood th5e the2" --> "Fo1r the2 g3ood 4of th5e pe6ople"
"" --> ""

## Solution:

    function order(words) {
        if (words == "") return words;
        const word = words.split(" ");
        let index,
            result = [],
            sorted = [],
            tempElement = [];
        word.forEach((element, i) => {
            [...element].forEach(
                (letter, j) => !isNaN(Number(letter)) && (index = Number(letter))
            );
            result[index - 1] = element;
        });
        return result.join(" ");
    }
