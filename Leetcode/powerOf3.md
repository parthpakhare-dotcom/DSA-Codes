
# LC3: Loops

## Problem Title:
<a href="https://leetcode.com/problems/power-of-three/description/">Power of Three</a>

## Problem Summary:
Given an integer n, return true if it is a power of three. Otherwise, return false.  
An integer n is a power of three, if there exists an integer x such that n == 3x.
## Approach
Suppose, you had a number that is a power of 3. It will means that, whenever you divide the number and you go on dividing it by 3, the remainder is always 0. This happens until the last quotient 1 appears.  
If the remainder is not zero at a point, return false.  
## Code

```cpp
class Solution {
public:
    bool isPowerOfThree(int n) {
        if (n<=0) return false;
        while (n!=1){
            int rem=n%3;
            if (rem!=0) return false;
            n/=3;
        }
        return true;
    }
};
```  
## Code Explanation
At closer inspection, we can observe that we didn't minimize the number till 0 as that will have the remainder 1 even fot a number like 27 at the end which falsely returns the answer as `false`. Here, the code runs log₃(n)-1 times at worse case for an actual power of 3. Thus, complexity is as below:  

## Complexity Analysis
- **Time Complexity:**  `O(log₃(n))` 
- **Space Complexity:** `O(1)`   _(No extra space taken)_

## Additional Notes
Question based on modulo operation.
