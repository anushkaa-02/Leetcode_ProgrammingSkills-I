# Subtract the Product and Sum of the digits
- ## Question:
>Given an integer number n, return the difference between the product of its digits and the sum of its digits.
- Example :

      Input: n = 234
      Output: 15 
      Explanation: 
      Product of digits = 2 * 3 * 4 = 24 
      Sum of digits = 2 + 3 + 4 = 9 
      Result = 24 - 9 = 15

- ## Solution:
```cpp
class Solution {
public:
    int subtractProductAndSum(int n) {
    int sum=0, product=1, digit, diff;
    while(n !=0)
        {
            digit=n%10;
            sum=sum+digit;
            product=product*digit;
            n=n/10;
        }
     diff=product-sum;
     return diff;
    }
};
```
## Tags
`Math`
