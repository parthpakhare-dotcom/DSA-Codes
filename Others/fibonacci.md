# Others: Loops, Conditonal Satements and Arrays

## Problem Title:
**Find the nth Fibonacci Number**

## Problem Summary:
Given an integer `n`, find the `n`th Fibonacci number.  
The Fibonacci sequence is defined as:  
- `F(0) = 0`  
- `F(1) = 1`  
- `F(n) = F(n-1) + F(n-2)` for `n >= 2`.  

For example, if `n = 5`, the sequence is `0, 1, 1, 2, 3`, and the 5th Fibonacci number is `3`.

## Approach:
To calculate the nth Fibonacci number:

1. Create a vector to store Fibonacci numbers up to index `n`.
2. Initialize the first two Fibonacci numbers, `0` and `1`.
3. Use a loop to calculate each Fibonacci number by adding the two previous numbers.
4. Handle the case when `n` is less than `2` separately, as the first two Fibonacci numbers are base cases.
5. Output the `n`th Fibonacci number.

The algorithm uses iteration and dynamic programming to avoid redundant calculations by storing already computed results.

## Code:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    int n;
    cout << "Give the number of the nth fibonacci number: ";
    cin >> n;

    vector<int> fib(n); // Create a vector of size n to store Fibonacci numbers
    fib[0] = 0;
    fib[1] = 1;

    for (int i = 2; i < n; i++) {
        fib[i] = fib[i - 1] + fib[i - 2]; // Calculate Fibonacci numbers
    }

    if (n < 2) {
        cout << "The nth fibonacci number is: " << n - 1 << endl;
    } else {
        cout << "The nth fibonacci number is: " << fib[n - 1] << endl;
    }

    return 0;
}
```  

## Code Explanation:  
- A vector fib of size n is used to store the Fibonacci sequence.  
- The first two elements are set as base cases: fib[0] = 0, fib[1] = 1.  
- A for loop from 2 to n-1 computes each Fibonacci number by adding the previous two elements.  
- For n < 2, it directly returns n - 1, which is 0 for n = 1 and -1 for n = 0.  
- For n >= 2, it outputs fib[n-1], which is the nth Fibonacci number according to 0-based indexing.  

## Complexity Analysis:  
- Time Complexity: O(n), since it computes each Fibonacci number from 2 to n-1.  

- Space Complexity: O(n), due to the vector storing all Fibonacci numbers up to n.  

This approach is efficient for small to moderate values of n and avoids recursion’s redundant recalculations.