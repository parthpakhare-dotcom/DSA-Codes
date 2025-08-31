# LC1: Loops

## Problem Title:
Add Digits

## Problem Summary:
Given a non-negative integer, repeatedly add all its digits until the result has only one digit. For example, given 38, the process is 3 + 8 = 11, then 1 + 1 = 2. Return the final single-digit result.
## Approach
Suppose, you had a number that will add up to only single digit at the end, obviosly, one will require the code to add all the digits.  
```cpp
int sum=0;
while (num){
    sum+=num%10;
    num/=10;
}
```  
But we need to do this until the number obtained is a single digit number, i.e. lower than or equal to 9. Until then, we have to run the above code. Thus, the final cod is:  
## Code

```cpp
class Solution {
public:
    int addDigits(int num) {
        
        while (num>9){
            int sum=0;
            while (num){
                sum+=(num%10);
                num/=10;
            }
            num=sum;
        }
        return num;
    }
};
```

## Code Explanation
As said earlier, we return the result of the inner loop as the number in the external loop until the number is greater then 9, i.e. a two digit number.  
Here, the outer loop takes relatively less iterations as any number quickly goes down to single digit in the _int_ range. The inner loop depends on how many orders of `10` is the inner no. Thus, complexity is as below:  

## Complexity Analysis
- **Time Complexity:**  `O(log₁₀(num))` 
- **Space Complexity:** `O(1)`   _(No extra space taken)_

## Additional Notes
Question based on modulo operation.