## CodeWars Multiples of 3 or 5

![code wars badge](https://www.codewars.com/users/FreePhoenix/badges/large)

#### [KATA](https://www.codewars.com/kata/514b92a657cdc65150000006)

### Description:

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in.

Note: If the number is a multiple of both 3 and 5, only count it once. Also, if a number is negative, return 0(for languages that do have them)

### Example:

    Kata.Solution(10) == 23


# C#

```CS
     public static class Kata
    {
        public static int Solution(int value)
        {
            if (value < 0) return 0;

            int result = 0;

            for (int i = 3; i < value; i++)
            {
                if(i % 3 == 0 || i % 5 == 0)
                {
                    result += i;
                }
            }

            return result;
        }
    }
 ```
