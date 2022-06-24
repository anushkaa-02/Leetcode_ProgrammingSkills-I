# Move Zeroes
>Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

- Example :

      Input: nums = [0,1,0,3,12]
      Output: [1,3,12,0,0]
      
- ## Solution:
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int x=0;
        for(int i=0; i<nums.size(); i++){
            if(nums[i]!=0)
                swap(nums[x++], nums[i]);
        }
    }
};
```
## Tags
`Array` `Two Pointers`
