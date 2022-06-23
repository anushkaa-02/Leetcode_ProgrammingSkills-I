# Check if it is a Straight Line
- ## Question:
>You are given an array `coordinates`, `coordinates[i] = [x, y]`, where `[x, y]` represents the coordinate of a point. Check if these points make a straight line in the XY plane.

- Example :

      Input: coordinates = [[1,2],[2,3],[3,4],[4,5],[5,6],[6,7]]
      Output: true
      
- ## Solution:
```cpp
class Solution {
public:
    bool checkStraightLine(vector<vector<int>>& points) {
        int len = points.size();
        if(len == 1) return false;
        if(len == 2) return true;
        int dx = points[1][0] - points[0][0], dy = points[1][1] - points[0][1];
        for(int i = 2; i < len; i++)
            if(dx*(points[i][1] - points[0][1]) != dy*(points[i][0] - points[0][0]))
                return false;
        return true;
    }
};
```

## Tags
`Array` `Math` `Geometry`
