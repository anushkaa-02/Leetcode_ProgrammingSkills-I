# Count Odd Numbers in an Interval Range
- ## Question:
>Given two non-negative integers low and high. Return the count of odd numbers between low and high (inclusive).
>>Constraints: 0 <= low <= high <= 10^9
- Example :
                                           
      Input: low = 3, high = 7
      Output: 3
      Explanation: The odd numbers between 3 and 7 are [3,5,7].

- ## Solution:
```cpp
class Solution {
public:
    int countOdds(int low, int high) {
    int output= (high-low)/2;
        if(low%2!=0 || high%2!=0)
            output++;
        return output;
    }
};
