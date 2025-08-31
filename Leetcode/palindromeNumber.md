# LC4: Number System

## Problem Title:
<a href="https://leetcode.com/problems/palindrome-number/description">Palindrome Number</a>

## Problem Summary:
Given an integer x, return true if x is a palindrome, and false otherwise.
## Approach
Firstly, a negative number cannot be a palindrome. Eg. palindrome of -121, i.e. 121- is not a "number".  
Next we first reverse the number, then check if it's same as the original number.  
## Code

```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        if (x<0){ //Negative numbers
            return 0;
        }
        int ans=0, num=x, rem;
        while (num){
            rem=num%10;
            num/=10;
            if (ans>INT_MAX/10) return false;
            ans=ans*10+rem;
        }
        if (ans==x) return true;
        else return false;
    }
};
```  
## Code Explanation
At closer inspection, we can observe that we checked if "ans>INT_MAX/10" for a possible answer to avoid intager overflow, like in the <a href="reverseInteger.md">Reverse Integer</a> problem. Since the no. of all loops while reversing the no. is depending on the no. of digits, the no of loops are based on ten's places. Thus, complexity is as below:  

## Complexity Analysis
- **Time Complexity:**  `O(log₁₀(|x|))` 
- **Space Complexity:** `O(1)`   _(No extra space taken)_

## Additional Notes
Question based on modulo operation.
