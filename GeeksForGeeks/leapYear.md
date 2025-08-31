# GFG1: Leap Year

## Problem Title:
<a href="https://www.geeksforgeeks.org/problems/leap-year0943/1">Leap Year</a>

## Problem Summary:
You are given an Integer n. Return true if It is a Leap Year otherwise return false. A leap year is divisible by 4, but not by 100 unless it is also divisible by 400.  
## Approach
If a century year like, say 1800, 1900 or 2000, the year should directly be divisible by 400 (both 4 and 100's LCM) and for the rest of the years (non-century), the only requirement is to be divisible by 4.  
## Code
```cpp
class Solution {
  public:
    bool checkYear(int n) {
        // code here
        if (n%400==0 || (n%4==0 && n%100!=0)){
            return true;
        }
        else return false;
    }
};
```

## Code Explanation
Two joined conditions.
## Complexity Analysis
- **Time Complexity:**  O(1)  
- **Space Complexity:**   O(1)

## Additional Notes
Basic Level question, needs factual awareness.