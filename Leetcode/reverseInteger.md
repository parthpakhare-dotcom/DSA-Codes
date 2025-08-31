# LC2: Loops

## Problem Title:
<a href="https://leetcode.com/problems/reverse-integer/">Reverse Integer</a>

## Problem Summary:
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.  
Assume the environment does not allow you to store 64-bit integers (signed or unsigned).
## Approach
Firstly, note that here we take the last part of a number (num mod 10) and add it to the 10 times of prev. answer, rising the order digits from units place in forward direction.    
```cpp
int ans=0;
while(x){
        int rem= x%10;
        ans=ans*10 + rem;
        x/=10;
    }
return ans;  
```  
But we need to do this considering that the reversed no, at any stage has not become greater that INTMax or INTMin. Eg. 2147003519, when reversed, becomes 9153007412, i.e. integer overflow. Thus, everytime we close the search if we see if:  
i) ans*10 + x%10 > INT-MAX: i.e. 
ans*10 > INT-MAX - x%10; i.e.  
ans > INT-MAX  (Since (x%10)/10==0 as (x%10) is 0-9)  OR  
ii) ans*10 + x%10 < INT-MIN: i.e. 
ans*10 < INT-MIN - x%10; i.e.  
ans <  INT-MIN
## Code

```cpp
class Solution {
public:
    int reverse(int x) {
        int ans=0;
        while(x){
            if (ans>INT_MAX/10 || ans<INT_MIN/10)
                return 0;
            else{
                int rem= x%10;
                ans=ans*10 + rem;
                x/=10;
            }
        }
        return ans;
    }
};
```

## Code Explanation
Since the no. of all loops while reversing the no. is depending on the no. of digits, the no of loops are based on ten's places. Eg: 143 (3 places) runs 3 times, 8542 runs 4 times, etc. Thus, the complexities are:   

## Complexity Analysis
- **Time Complexity:**  `O(log₁₀(|x|))` 
- **Space Complexity:** `O(1)`   _(No extra space taken)_

## Additional Notes
Question based on modulo operation and edge-case handling.