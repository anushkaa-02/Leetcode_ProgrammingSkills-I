# Average Salary Excluding the Minimum and Maximum Salary
- ## Question:
>You are given an array of unique integers salary where salary[i] is the salary of the ith employee.

>Return the average salary of employees excluding the minimum and maximum salary. Answers within 10-5 of the actual answer will be accepted.
- Example :

      Input: salary = [4000,3000,1000,2000]
      Output: 2500.00000
      Explanation: Minimum salary and maximum salary are 1000 and 4000 respectively.
      Average salary excluding minimum and maximum salary is (2000+3000) / 2 = 2500


- ## Solution:
```cpp
class Solution {
public:
    double average(vector<int>& salary) {
        int n = salary.size();
        sort(salary.begin(),salary.end());
        int s=0;
        for(int i=1;i<n-1;i++)
            s+=salary[i];
        double P = (double)s/(n-2);
        return P;   
    }
};
