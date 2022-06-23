# Next Greater Element I 
- ## Question:
>The next greater element of some element x in an array is the first greater element that is to the right of x in the same array.
>
>You are given two distinct 0-indexed integer arrays nums1 and nums2, where nums1 is a subset of nums2.
>
>For each 0 <= i < nums1.length, find the index j such that nums1[i] == nums2[j] and determine the next greater element of nums2[j] in nums2. If there is no next >greater element, then the answer for this query is -1.
>
>Return an array ans of length nums1.length such that ans[i] is the next greater element as described above.


- Example :

      Input: nums1 = [4,1,2], nums2 = [1,3,4,2]
      Output: [-1,3,-1]
      Explanation: The next greater element for each value of nums1 is as follows:
      - 4 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.
      - 1 is underlined in nums2 = [1,3,4,2]. The next greater element is 3.
      - 2 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.

- ## Solution:
```cpp
class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
        vector<int> np(1e4+1, 0);
        vector<int> ans;
        stack<int> s;
        for(int i=0; i<nums1.size(); i++){
            np[nums1[i]]=1;
        }
        for(int i=0; i<nums2.size(); i++){
            while(!s.empty() && nums2[i]>s.top()){
                int x = s.top();
                if(np[x]){
                    np[x]=nums2[i];
                }
                s.pop();
            }
            s.push(nums2[i]);
        }
        while(!s.empty()){
            int x = s.top();
            if(np[x]){
                np[x]=-1;
            }
            s.pop();
        }
        for(int i=0; i<nums1.size(); i++){
            ans.push_back(np[nums1[i]]);
        }
        return ans;
    }
};
```

## Tags
`Array` `Hash Table` `Stack`

