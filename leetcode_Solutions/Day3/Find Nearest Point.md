# Find Nearest Point That Has the Same X or Y Coordinate
- ## Question:
> You are given two integers, x and y, which represent your current location on a Cartesian grid: (x, y). You are also given an array points where each points[i] = [ai, bi] represents that a point exists at (ai, bi). A point is valid if it shares the same x-coordinate or the same y-coordinate as your location.

>Return the index (0-indexed) of the valid point with the smallest Manhattan distance from your current location. If there are multiple, return the valid point with the smallest index. If there are no valid points, return -1.

>The Manhattan distance between two points (x1, y1) and (x2, y2) is abs(x1 - x2) + abs(y1 - y2).

- Example :

      Input: x = 3, y = 4, points = [[1,2],[3,1],[2,4],[2,3],[4,4]]
      Output: 2
      Explanation: Of all the points, only [3,1], [2,4] and [4,4] are valid. Of the valid points, [2,4] and [4,4] have the 
      smallest Manhattan distance from your    current location, with a distance of 1. [2,4] has the smallest index, so return 2.
      
- ## Solution:
```cpp
class Solution {
public:
    int nearestValidPoint(int x, int y, vector<vector<int>>& points) {
        int pos = -1;                                          
        int ans = INT_MAX;                                   
        for(int i = 0; i < points.size();i++)                  
        {
            if(x == points[i][0] || y == points[i][1])        
            {
                int dist = abs(x-points[i][0]) + abs(y-points[i][1]);       
            
                if(dist < ans)                                 
                {
                    ans = dist;
                    pos = i;
                }           
            }
        }
        return pos;                                        
    }
};
```
## Tags
`Array`
