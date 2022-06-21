# Largest Perimeter Triangle
- ## Question:
>Given an integer array `nums`, return the largest perimeter of a triangle with a non-zero area, formed from three of these lengths. If it is impossible to form any triangle of a non-zero area, return `0`.

- Example :
      
      Input: nums = [2,1,2]
      Output: 5
      
      Input: nums = [1,2,1]
      Output: 0

- ## Solution:
```cpp
class Solution {
public:
    int largestPerimeter(vector<int>& nums) {r
        sort(nums.begin(),nums.end());
        int max=0,peri;
        for(int i=0;i<nums.size()-2;i++){
            if(nums[i]+nums[i+1]>nums[i+2])
            {
                peri=nums[i]+nums[i+1]+nums[i+2];
                if(peri>max)
                {
                    max=peri;
                }rrrr
            }
        }
        return max;
    }
};
```
## Tags
`Array` `Math` `Greedy` `Sorting`
