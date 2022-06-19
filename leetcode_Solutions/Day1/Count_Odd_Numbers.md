```cpp
class Solution {
public:
    int countOdds(int low, int high) {
    int output= (high-low)/2;
        if(low%2!=0 || high%2!=0)
            output++;
        return output;
    }
};