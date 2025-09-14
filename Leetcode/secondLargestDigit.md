# LC7: Loops and Conditional Statements

## Problem Title:
**<a href="https://leetcode.com/problems/second-largest-digit-in-a-string/description/">Second Largest Digit in a String</a>**

## Problem Summary:
Given a string `s` consisting of alphanumeric characters, find the second largest digit that appears in the string.  
- If there is no second largest digit, return -1.

Example:

Input: s = "dfa12321afd"  
Output: 2  
Explanation: The digits present are 1, 2, and 3. The largest is 3, and the second largest is 2.

Input: s = "abc1111"  
Output: -1  
Explanation: The only digit present is 1, so no second largest digit exists.

## Approach
The problem can be solved by tracking which digits are present in the string and then finding the largest and second largest among them.

Steps:
1. Create a boolean array `numdigits` of size 10 to record which digits from 0 to 9 are present.
2. Iterate over the string and for each character, check if it is a digit using `isdigit()`.
3. If it is a digit, convert it to an integer and mark its presence in the `numdigits` array.
4. After processing the string, iterate from 9 down to 0 to find the largest digit (`first`) and the second largest digit (`second`).
5. Return `second` if found, or -1 if there is no second largest digit.

## Code

```cpp
class Solution {
public:
    int secondHighest(string s) {
        vector<bool> numdigits(10, 0);
        for (int i = 0; i < s.size(); i++) {
            if (isdigit(s[i])) {
                int num = s[i] - '0';
                numdigits[num] = 1;
            }
        }
        
        int first = -1, second = -1;
        for (int i = 9; i >= 0; i--) {
            if (numdigits[i]) {
                if (first == -1) {
                    first = i;
                } else {
                    second = i;
                    break;
                }
            }
        }
        
        return second;
    }
};
```

## Code Explanation

- A vector numdigits of size 10 is initialized to track which digits exist in the input string.
- The loop iterates over each character in the string:  
- If the character is a digit, it is converted to an integer and marked as present.  
- The second loop starts from 9 and goes down to 0 to find the largest (first) and second largest (second) digits.  
- Once the first largest is found, the next one found is the second largest, and the loop is exited.  
- Finally, the function returns the second largest digit if it exists or -1 if it doesn’t.  

## Complexity Analysis

- Time Complexity: O(n), where n is the length of the input string. The string is traversed twice, but both are linear scans.  
- Space Complexity: O(1), as the array numdigits is of fixed size 10.  

## Additional Notes

This problem is a good exercise in string manipulation and using arrays to efficiently track occurrences. The solution is simple yet effective, making use of basic data structures and control flow.
