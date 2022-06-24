# Richest Customer Wealth
- ## Question:
>You are given an `m x n` integer grid accounts where accounts [i][j] is the amount of money the `ith` customer has in the `jth` bank. Return the wealth that the richest customer has.
>
>A customer's wealth is the amount of money they have in all their bank accounts. The richest customer is the customer that has the maximum wealth.

- Example:

      Input: accounts = [[1,2,3],[3,2,1]]
      Output: 6
      Explanation:
      1st customer has wealth = 1 + 2 + 3 = 6
      2nd customer has wealth = 3 + 2 + 1 = 6
      Both customers are considered the richest with a wealth of 6 each, so return 6.
      
- ## Solution:
```cpp
class Solution {
public:
    int maximumWealth(vector<vector<int>>& accounts) {
        int maxi = -1;
        for(int i=0;i<accounts.size();i++){
            int sum =0;
            for(int j =0;j<accounts[i].size();j++){
                sum +=accounts[i][j];
            }
            maxi = max(maxi,sum);
        }
        return maxi;
    }
};
```
## Tags
`Array` `Matrix`
