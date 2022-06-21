# Number of 1 bits
- ## Question:
>Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).
- Example :

      Input: n = 00000000000000000000000000001011
      Output: 3
      Explanation: The input binary string 00000000000000000000000000001011 has a total of three '1' bits.

- ## Solution:
```cpp
class Solution {
public:
    int hammingWeight(uint32_t n) {
        int ans = 0;
        while(n > 0)
        {
            if(n%2==1)
            ans++;
            n /= 2;
        }
        return ans;
    }
};
```

## Tags
`Bit Manipulation`
