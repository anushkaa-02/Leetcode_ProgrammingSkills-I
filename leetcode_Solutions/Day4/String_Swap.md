# Check if One String Swap Can Make Strings Equal
- ## Question:
>You are given two strings `s1` and `s2` of equal length. A string swap is an operation where you choose two indices in a string (not necessarily different) 
>and swap the characters at these indices.
>
>Return `true` if it is possible to make both strings equal by performing at most one string swap on exactly one of the strings. Otherwise, return `false`.

- Example :

      Input: s1 = "bank", s2 = "kanb"
      Output: true
      Explanation: For example, swap the first character with the last character of s2 to make "bank".
      
- ## Solution:
```cpp
class Solution {
	public:
		bool areAlmostEqual(string s1, string s2) 
		{
			int j=0,length=0;
			for(int i=0;i<s1.size();i++)
			{
				if(s1[i]==s2[i])
					continue;
				length++;
			}
			sort(s1.begin(),s1.end());
			sort(s2.begin(),s2.end());
			if((length==2 || length==0) && s1==s2)
				return true;
			else
				return false;
		}
	};
  ```
  
  ## Tags
  `Hash Table` `String` `Counting`
