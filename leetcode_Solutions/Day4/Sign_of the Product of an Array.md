# Sign of the Product of an Array
- ## Question:
>There is a function `signFunc(x)` that returns

- 1 if x is positive.
- -1 if x is negative.
- 0 if x is equal to 0.

>You are given an integer array nums. Let product be the product of all values in the array nums. 
>
>Return signFunc(product)

- Example :

      Input: nums = [1,5,0,2,-3]
      Output: 0
      Explanation: The product of all values in the array is 0, and signFunc(0) = 0

- ## Solution:
```cpp
class Solution {
	public:
	int arraySign(vector<int>& nums) 
	    {
		    double product=1;
			for(int i=0;i<nums.size();i++)
				{
					product=product*nums[i];
				}
			return signFunc(product);
		}
	int signFunc(double x)
		{
		    if(x>0)
				return 1;
			else if(x<0)
				return -1;
			else
				return 0;
		}
	};
```

## Tags
`Array` `Math`
