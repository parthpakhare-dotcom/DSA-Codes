# GFG2: Loops
## Problem Title:
<a href="https://www.geeksforgeeks.org/problems/missing-number-in-shuffled-array/">Missing Number in Shuffled Array</a>

## Problem Summary:
You are given two arrays:  
- `arr1` of size `n`  
- `arr2` of size `n-1`  

Both arrays contain the same set of integers except that `arr2` is formed by shuffling `arr1` and removing exactly one element.  
Your task is to find the missing number from `arr2`.

## Approach
The problem can be solved by observing that if we take the sum of all elements in `arr1` and subtract the sum of elements in `arr2`, the difference will be the missing element. This is because both arrays initially contained the same numbers, except one missing in `arr2`.

Steps:  
1. Compute the sum of elements of `arr1`.  
2. Compute the sum of elements of `arr2`.  
3. The missing number is `sum(arr1) - sum(arr2)`.

## Code
```cpp
class Solution {
  public:
    int findMissing(vector<int>& arr1, vector<int>& arr2) {
        // your code
        int sum1=0, sum2=0;
        for (int i=0; i<arr1.size(); i++){
            sum1+=arr1[i];
        }
        for (int i=0; i<arr2.size(); i++){
            sum2+=arr2[i];
        }
        return (sum1-sum2);
    }
};

```

## Code Explanation
- `sum1` stores the total of all elements in the larger array.  
- `sum2` stores the total of all elements in the smaller array.  
- The missing element is simply `sum1 - sum2`, since every other element cancels out.

## Complexity Analysis
- **Time Complexity:** O(n), since we traverse both arrays once.  
- **Space Complexity:** O(1), as only constant extra space is used.

## Additional Notes
This is a simple but effective approach. Alternative methods include using **XOR** of all elements, which also gives the missing number efficiently.  

```cpp
class Solution {
  public:
    int findMissing(vector<int>& arr1, vector<int>& arr2) {
        // your code
        int sum1=0, sum2=0;
        for (int i=0; i<arr1.size(); i++){
            sum1^=arr1[i];
        }
        for (int i=0; i<arr2.size(); i++){
            sum2^=arr2[i];
        }
        return (sum1^sum2);
    }
};
```