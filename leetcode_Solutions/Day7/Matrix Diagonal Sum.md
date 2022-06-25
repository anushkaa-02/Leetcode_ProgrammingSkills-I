# Matrix Diagonal Sum
- ## Question:
>Given a square matrix `mat`, return the sum of the matrix diagonals.
>
>Only include the sum of all the elements on the primary diagonal and all the elements on the secondary diagonal that are not part of the primary diagonal.

- Example :

       Input: mat = [[1,2,3],
                     [4,5,6],
                     [7,8,9]]
      Output: 25
      Explanation: Diagonals sum: 1 + 5 + 9 + 3 + 7 = 25
      Notice that element mat[1][1] = 5 is counted only once.
      
- ## Solution:
```cpp
class Solution {
		public:
			int diagonalSum(vector<vector<int>>& v)
			{
				int sum=0;
				for(int i=0;i<v.size();i++)
					sum+=v[i][i];
				for(int j=0;j<v[0].size();j++)
				{
					if(j!=v.size()-1-j)
						sum=sum+v[j][v.size()-1-j];
				}
				 return sum;
			}

	 };
```

## Tags
`Array` `Matrix`
      
