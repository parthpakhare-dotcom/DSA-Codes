# LC6: Loops

## Problem Title:
**<a href="https://leetcode.com/problems/factorial-trailing-zeroes/description/">Factorial Trailing Zeroes</a>**

## Problem Summary:
Given an integer n, return the number of trailing zeroes in n!.
Example:

Input: n = 5
Output: 1
Explanation: 5! = 120, one trailing zero.

## Approach
Since the no. has trailing zeros for n! only if it is a multiple of 10, the number must have 10 in its factor, i.e. 2x5 as a factor pair. Now, starting 5!, there are always more 2s than 5s, the number of 0s in trailing will also only depend upon the number of 5s. Thus we have to finfd the number of 5s in multiples.  
Eg 1: 7!=1x2x3x4x5x6x7 so, we getcount of 5=1; thus, one trailing zero.  
Eg 2: 15!= 1x2x3x4x5x6x7x8x9x10x11x12x13x14x15  
         = 1x2x3x4x5x6x7x8x9x(2x5)x11x12x13x14x(3x5)  Thus, 3 trailing zeros.  
Eg 3: 50!= 1x2x3x4x......24x25x26x....48x49x50  
         = 1x2x3x4x......24x(5x5)x26x..x(2x5x5)  Thus, in total, 120 trailing zeros will be there. Quite, a large number!  
Thus we notice that, we consider all the multiples of the 5 among the factors. But note that unlike initial multiples like 10, 15, 20, etc. we also have other ones like 25 or 50 with multiple number of 5s in them.  
  
## Code

```cpp
class Solution {
public:
    int trailingZeroes(int n) {
        if (n<5){
            return 0;
        }
        else{
            int count= 0;
            while (n>=5){
                count+=n/5;
                n/=5;
            }
            return count;
        }
    }
};
```

## Code Explanation
As seen above, after each arrival of a multiple of 5 we add the number of 5s in that multiple.  
The code goes until, n becomes 0 by dividing it to 5 iteratively. Thus, complexity is as below:  

## Complexity Analysis
- Time Complexity: O(log_5 n) = O(log n) — the loop runs once per power of 5 up to n.  
- Space Complexity: O(1) — constant extra space.

## Additional Notes
Question based on modulo and XOR operation.