## CodeWars Split Strings

![code wars badge](https://www.codewars.com/users/FreePhoenix/badges/large)

#### [KATA](https://www.codewars.com/kata/515de9ae9dcfc28eb6000001)

### Description:

Complete the solution so that it splits the string into pairs of two characters.
If the string contains an odd number of characters then it should replace the missing second character of the final pair with an underscore ('_').

### Example:

    SplitString.Solution("abc"); // should return ["ab", "c_"]
    SplitString.Solution("abcdef"); // should return ["ab", "cd", "ef"]


# C#

## Solution 1

```CS
using System;

public class SplitString
{
	public static string[] Solution(string str)
	{
		string[] result = new string[(int)Math.Ceiling((double)str.Length / 2)];
		int resultPosition = 0;
        
        // If not even length append '_'
		if (str.Length % 2 != 0)
		{
			str += '_';
		}

        // Pushes symbol pairs from string to array
		for (int i = 0; i < str.Length; i += 2)
		{
			result[resultPosition++] = new string (new char[]{str[i], str[i + 1]});
		}

		return result;
	}
}
 ```

## Solution 2

```CS
using System.Text.RegularExpressions;
using System.Linq;

public class SplitString
{
    public static string[] Solution(string str)
    {
        // If not even length append '_'
        if (str.Length % 2 != 0)
        {
            str += "_";
        }
        
        // Puts symbol pairs to the array and returns
        return Regex.Matches(str, @"\w{2}").Select(m => m.Value).ToArray();
    }
}
 ```
