## CodeWars #14 Playing with digits!

![code wars badge](https://www.codewars.com/users/FreePhoenix/badges/large)

#### [kata](https://www.codewars.com/kata/playing-with-digits/javascript)

### Description:

Some numbers have funny properties. For example:

89 --> 8¹ + 9² = 89 \* 1

695 --> 6² + 9³ + 5⁴= 1390 = 695 \* 2

46288 --> 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 _ 51
Given a positive integer n written as abcd... (a, b, c, d... being digits) and a positive integer p we want to find a positive integer k, if it exists, such as the sum of the digits of n taken to the successive powers of p is equal to k _ n. In other words:

Is there an integer k such as : (a ^ p + b ^ (p+1) + c ^(p+2) + d ^ (p+3) + ...) = n \* k
If it is the case we will return k, if not return -1.

Note: n, p will always be given as strictly positive integers.

### Example:

digPow(89, 1) should return 1 since 8¹ + 9² = 89 = 89 \* 1  
digPow(92, 1) should return -1 since there is no k such as 9¹ + 2² equals 92 _ k  
digPow(695, 2) should return 2 since 6² + 9³ + 5⁴= 1390 = 695 _ 2  
digPow(46288, 3) should return 51 since 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 \* 51

## 1 Solution:

function digPow(number, power) {
	let stringN = String(number)
		.split("")
		.reduce((acc, value, i) => acc + Math.pow(value, power + i), 0);
	return x % number ? -1 : x / number;
}

## 2 Solution:

    function digPow(n, p){
    let digits = n.toString();
    let result = 0;
    for(let i = 0; i < digits.length; i++){
    	let number = parseInt(digits.charAt(i),10);
    	result += Math.pow(digits[i], i + p)
    }
    let originalPow = Math.pow(n, p);
    if(result == originalPow){
    	return p;
    } else if(result%n === 0) {
    	return result / n;
    } else {
    	return -1;
    }
    }
