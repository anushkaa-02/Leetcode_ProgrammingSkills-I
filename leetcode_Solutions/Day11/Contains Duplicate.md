# Contains Duplicate
- ## Question:
>Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

- Example :

      Input: nums = [1,2,3,1]
      Output: true
      
- ## Solution:
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        bool a = false;
        for(int i = 0;i<nums.size()-1;i++){
            if(nums[i]==nums[i+1]){
                a = true;
                break;
            }  
        }
     return a;   
    }
};
```

## Tags
`Array` `Hash Table` `Sorting`
