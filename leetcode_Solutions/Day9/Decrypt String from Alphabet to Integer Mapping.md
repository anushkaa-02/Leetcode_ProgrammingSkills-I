# Decrypt String from Alphabet to Integr Mapping
- ## Question:
>You are given a string s formed by digits and `'#'`. We want to map s to English lowercase characters as follows:
>
- Characters ('a' to 'i') are represented by ('1' to '9') respectively.
- Characters ('j' to 'z') are represented by ('10#' to '26#') respectively.
- Return the string formed after mapping.
>
>The test cases are generated so that a unique mapping will always exist.

- Example :

      Input: s = "10#11#12"
      Output: "jkab"
      Explanation: "j" -> "10#" , "k" -> "11#" , "a" -> "1" , "b" -> "2".
      
- ## Solution:
```cpp
class Solution {
public:
    string freqAlphabets(string s) {
        string res="";
        for(int i=s.length()-1;i>=0;)
        {
            if(s[i]!='#')
            {
                char ch=char(s[i]-'0'+96);
                res+=ch;
                i--;
            }
            else{ 
                int x = stoi(s.substr(i-2, 2));
                 res+=char(96+x);
                 i=i-3;
               
            }
                
        }
        reverse(res.begin(),res.end());
        return res;
    }
};
```

## Tags

`String`
      
