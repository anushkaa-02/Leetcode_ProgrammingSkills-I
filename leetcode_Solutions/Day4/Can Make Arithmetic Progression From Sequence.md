# Can Make Arithmetic Progression From Sequence
- ## Question:
>A sequence of numbers is called an arithmetic progression if the difference between any two consecutive elements is the same.
>
>Given an array of numbers `arr`, return `true` if the array can be rearranged to form an arithmetic progression. Otherwise, return `false`.

- Example :

      Input: arr = [3,5,1]
      Output: true
      Explanation: We can reorder the elements as [1,3,5] or [5,3,1] with differences 2 and -2 respectively, between each consecutive elements.
      
- ## Solution:
```cpp
class Solution {
public:
    bool canMakeArithmeticProgression(vector<int>& v) {
        sort(v.begin(),v.end());
        int d=v[1]-v[0];
        for(int i=0;i<v.size()-1;i++)
        {
            if(v[i+1]-v[i]!=d)
                return 0;  
        }
        return 1;
    }
};
```
## Tags
`Array` `Sorting`
