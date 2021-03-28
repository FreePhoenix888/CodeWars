## CodeWars Sort the odd

![code wars badge](https://www.codewars.com/users/FreePhoenix/badges/large)

#### [KATA](https://www.codewars.com/kata/578aa45ee9fd15ff4600090d)

### Description:

You will be given an array of numbers. You have to sort the odd numbers in ascending order while leaving the even numbers at their original positions.

### Example:

    [7, 1]  =>  [1, 7]
    [5, 8, 6, 3, 4]  =>  [3, 8, 6, 5, 4]
    [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]  =>  [1, 8, 3, 6, 5, 4, 7, 2, 9, 0]


# C#

## Solution 1

```CS
using System;

public class Kata
{
    public static int[] SortArray(int[] array)
    {
        int[] oddArr = new int[array.Length];
        int oddArrPosition = 0;

        // Puts odd elements into oddArr
        for (int i = 0; i < array.Length; i++)
        {
            if(array[i] % 2 != 0)
            {
                oddArr[oddArrPosition++] = array[i];
            }
        }

        Array.Resize(ref oddArr, oddArrPosition);
        Array.Sort(oddArr);

        // Put elements from the sorted odd elements array into the result array
        oddArrPosition = 0;
        for (int i = 0; i < array.Length; i++)
        {
            if (array[i] % 2 != 0)
            {
                array[i] = oddArr[oddArrPosition++];
            }
        }

        return array;
    }
}
 ```

## Solution 2

```CS
using System.Collections.Generic;
using System.Linq;

public class Kata
{
    public static int[] SortArray(int[] array)
    {
        Queue<int> oddInts = new Queue<int>(array.Where(n => n % 2 != 0).OrderBy(n => n));

        return array.Select(n => n % 2 != 0 ? oddInts.Dequeue() : n).ToArray();
    }
}
 ```


