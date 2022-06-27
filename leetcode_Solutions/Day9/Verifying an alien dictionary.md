# Verifying an alien dictionary
- ## Question:
>In an alien language, surprisingly, they also use English lowercase letters, but possibly in a different order. The order of the alphabet is some permutation of >lowercase letters.
>
>Given a sequence of words written in the alien language, and the order of the alphabet, return true if and only if the given words are sorted lexicographically in this alien language.

- Example :

      Input: words = ["hello","leetcode"], order = "hlabcdefgijkmnopqrstuvwxyz"
      Output: true
      Explanation: As 'h' comes before 'l' in this language, then the sequence is sorted.
      
- ## Solution:
```cpp
class Solution {
public:
    bool isAlienSorted(vector<string>& words, string order) {
        int n = words.size();
        map<char, char> mp;
        for (int i=0; i<26; i++){
            mp[order[i]] = 'a'+i;
        }
        for (int i=0; i<n; i++){
            for (int j=0; j<words[i].length(); j++){
                words[i][j] = mp[words[i][j]];
            }
        }
        for (int i=1; i<n; i++){
            if (words[i]<words[i-1]){
                return false;
            }
        }
        return true;
    }
};
```

## Tags
`Array` `Hash table` `String`
