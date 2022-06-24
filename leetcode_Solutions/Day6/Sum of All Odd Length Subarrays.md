# Sum of All Odd Length Subarrays
- ## Question:
>Given an array of positive integers arr, return the sum of all possible *odd-length subarrays of arr*.
>
>A **subarray** is a contiguous subsequence of the array.

- Example :

      Input: arr = [1,4,2,5,3]
      Output: 58
      Explanation: The odd-length subarrays of arr and their sums are:
      [1] = 1
      [4] = 4
      [2] = 2
      [5] = 5
      [3] = 3
      [1,4,2] = 7
      [4,2,5] = 11
      [2,5,3] = 10
      [1,4,2,5,3] = 15
      If we add all these together we get 1 + 4 + 2 + 5 + 3 + 7 + 11 + 10 + 15 = 58
      
- ## Solution:
```cpp
class Solution {
public:
    int sumOddLengthSubarrays(vector<int>& arr) {
        int count=0;
        for(int i=1;i<=arr.size();i=i+2){
            int j=0;
            while((j+i)<=arr.size()){
                for(int k=j;k<(j+i);k++){
                    count+=arr[k];
                }j++;
            }
        }
        return count;
    }
};
```

## Tags
`Array` `Math` `Prefix Sum`
