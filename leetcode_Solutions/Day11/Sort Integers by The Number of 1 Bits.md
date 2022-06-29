# Sort Integers by The Number of 1 Bits
- ## Question:
>You are given an integer array arr. Sort the integers in the array in ascending order by the number of 1's in their binary representation and in case of two or more >integers have the same number of 1's you have to sort them in ascending order.
>
>Return the array after sorting it.

- Example :

      Input: arr = [0,1,2,3,4,5,6,7,8]
      Output: [0,1,2,4,8,3,5,6,7]
      Explantion: [0] is the only integer with 0 bits.
      [1,2,4,8] all have 1 bit.
      [3,5,6] have 2 bits.
      [7] has 3 bits.
      The sorted array by bits is [0,1,2,4,8,3,5,6,7]
      
- ## Solution:
```cpp
class Solution {
public:
	vector<int> sortByBits(vector<int>& nums) {
		vector<pair<int,int>>v;
		for(int i=0;i<nums.size();i++) v.push_back({__builtin_popcount(nums[i]),nums[i]});
		sort(v.begin(),v.end(),[](pair<int,int>p1,pair<int,int>p2){
			if(p1.first==p2.first)return p1.second<p2.second;
			return p1.first<p2.first;
		});
		for(int i=0;i<v.size();i++) nums[i]=v[i].second;
		return nums;
	}
};
```

## Tags
`Array` `Bit Manipulation` `Sorting`