# Others: Loops

## Problem Title:
**Armstrong Number Check**

## Problem Summary:
Given an integer `n`, determine whether it is an Armstrong number.  
An Armstrong number of `d` digits is a number such that the sum of its digits each raised to the power `d` is equal to the number itself.  
For example, `153` is an Armstrong number because `1³ + 5³ + 3³ = 153`.

## Approach:
To check if a number is an Armstrong number:

1. First, count the number of digits `d` in `n`.
2. Then, calculate the sum of each digit raised to the power `d`.
3. Compare the calculated sum with the original number.  

If they are equal, `n` is an Armstrong number; otherwise, it is not.

The algorithm:

- Use a helper function to count the digits.
- Use another loop to calculate the powered sum.
- Finally, compare and return the result.

## Code:

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int countDigits(int n){
    int count = 0;
    while(n){
        count++;
        n /= 10;
    }
    return count;
}

bool isArmstrong(int n){
    int count = countDigits(n);  // for the power
    int ans = 0;                 // for checking later
    int test = n;                // to carry out the test
    while (test){
        int digit = test % 10;
        ans += pow(digit, count);
        test /= 10;
    }
    return ans == n;
}

int main()
{
    cout << "Enter the number:" << endl;
    int n;
    cin >> n;
    cout << "Is it an Armstrong Number?" << endl;
    cout << isArmstrong(n);
    return 0;
}
```  

## Code Explanation: 
- countDigits(int n) counts the number of digits by dividing the number by 10 repeatedly.  
- isArmstrong(int n) uses this count to calculate the sum of digits raised to that power.  
- It iterates over each digit, extracts it using modulus operation (%), and adds the powered value to ans.  
- After the loop, it checks if the calculated sum equals the original number and returns the result.  

## Complexity Analysis:  
- Time Complexity: O(d) where d is the number of digits in n. The loop runs once to count digits and once to compute the sum.  
- Space Complexity: O(1) (only a few integer variables are used).