# Reshape the Matrix
- ## Question:

>In MATLAB, there is a handy function called `reshape` which can reshape an `m x n` matrix into a new one with a different size `r x c` keeping its original data.
>
>You are given an `m x n` matrix mat and two integers `r` and `c` representing the number of rows and the number of columns of the wanted reshaped matrix.
>
>The reshaped matrix should be filled with all the elements of the original matrix in the same row-traversing order as they were.
>
>If the `reshape` operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.

- Example :

      Input: mat = [[1,2],[3,4]], r = 1, c = 4
      Output: [[1,2,3,4]]
      
- ## Solution:
```cpp
class Solution {
public:
    vector<vector<int>> matrixReshape(vector<vector<int>>& mat, int r, int c) {
		
		//base condition
        if(mat.size()*mat[0].size()!=r*c){
            return mat;
        }
        vector<vector<int>> arr;
        
		//initializing the vector
        for(int i=0;i<r;i++){
            vector<int> temp;
            for(int j=0;j<c;j++){
                temp.push_back(0);
            }
            arr.push_back(temp);
        }
        
		//main loop
        for( int i = 0; i< mat.size(); i++){
            for( int j =0; j < mat[0].size(); j++){
                int k = i*mat[0].size()+j;
                arr[k/c][k%c]=mat[i][j];
            }
        }
		
        return arr;
    }
};
```

## Tags
`Array` `Matrix` `Simulation`
