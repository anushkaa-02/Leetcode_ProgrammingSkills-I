# Valid Anagram
- ## Question:
>Given two strings `s` and `t`, return `true` if t is an anagram of `s`, and `false` otherwise.
>
>An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

- Example :

      Input: s = "anagram", t = "nagaram"
      Output: true
      
- ## Solution:
```cpp
class Solution {
public:
    bool isAnagram(string s, string t) 
      {
	      sort(t.begin(), t.end());
	      sort(s.begin(), s.end());
	      return s == t ? 1 : 0;
      }
};
```

## Tags
`Hash Table` `Sorting` `String`
