# LC5: Number Systems

## Problem Title:
**<a href="https://leetcode.com/problems/complement-of-base-10-integer/">Complement of Base 10 Integer</a>**

## Problem Summary:
The complement of an integer is the integer you get when you flip all the 0's to 1's and all the 1's to 0's in its binary representation.

For example, The integer 5 is "101" in binary and its complement is "010" which is the integer 2.
Given an integer n, return its complement.
## Approach
Since the no. came from a base 10 number system, for its complement, we first need a base 2 equivalent. We can serially obtain these bits by taking mod w.r.t 2 for the number until it becomes 0 by dividing. Meanwhile, to alter each bit (nature of any complement), we XOR it with 1. This makes 1 to 0 and vice versa. Later, in the same step, we use the same bit to convert the no. back to the decimal for,. We know that, we serially from LSB to MSB, mutiply bits by powers of 2. Same we do here to obtain the answer number with altered bits.
 
## Code

```cpp
class Solution {
public:
    int bitwiseComplement(int n) {
        int ans=0, mul=1;
        while (n){
            int rem= n%2;
            rem=rem^1;
            ans=ans*mul+rem;
            mul*=2;
            n/=2;
        }
    }
};
```

## Code Explanation
As seen above, the code goes until, n becomes 0 by dividing it to 2 iteratively. Thus, complexity is as below:  

## Complexity Analysis
- **Time Complexity:**  `O(log₂(n))` 
- **Space Complexity:** `O(1)`   _(No extra space taken)_

## Additional Notes
Question based on modulo and XOR operation.