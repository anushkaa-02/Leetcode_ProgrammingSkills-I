# Merge Strings Alternately
- ## Question:
>You are given two strings `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with `word1`. If a string is longer than the other, append the additional letters onto the end of the merged string.
>
>Return the merged string.

- Example :

      Input: word1 = "abc", word2 = "pqr"
      Output: "apbqcr"
      Explanation: The merged string will be merged as so:
      word1:  a   b   c
      word2:    p   q   r
      merged: a p b q c r
      
- ## Solution:
```cpp
class Solution {
public:
      string mergeAlternately(string word1, string word2) 
	{
	 int s1=word1.size();
	 int s2=word2.size();
	 string ans;
	 for(int i=0;i<min(s1,s2);i++)
		{
		  ans.push_back(word1[i]);
		  ans.push_back(word2[i]);
		}
	if(s1>s2)
		{
       		 for(int i=s2;i<s1;i++)
		 ans.push_back(word1[i]);
		}
	else if(s2>s1)
		{
		 for(int i=s1;i<s2;i++)
		 ans.push_back(word2[i]);
		}
		return ans;
		}
	};
 ```
 
 ## Tags
 `Two Pointers` `String`
