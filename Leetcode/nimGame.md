# LC7: Loops

## Problem Title:
**<a href="https://leetcode.com/problems/nim-game/description/">Nim Game</a>**

## Problem Summary:
You are playing the Nim game with your friend. The rules are as follows:
- There is a heap of `n` stones.
- On each player's turn, they can remove 1 to 3 stones from the heap.
- The player who removes the last stone wins.

Given the integer `n`, return `true` if you can win the game when you take the first turn, assuming both players play optimally.

Example:

Input: n = 4  
Output: false  
Explanation: If there are 4 stones, no matter how many stones you remove (1 to 3), your friend can always remove the remaining stones and win.

## Approach
The problem is a classic mathematical game problem based on modular arithmetic.

- The key observation is that if `n` is a multiple of 4 (i.e., `n % 4 == 0`), you cannot win if your opponent plays optimally.  
- For all other cases, you can always win by removing the right number of stones to leave a multiple of 4 for your opponent.

Thus, the solution boils down to checking if `n` is a multiple of 4 or not.

## Code

```cpp
class Solution {
public:
    bool canWinNim(int n) {
        if (n % 4 == 0){
            return false;
        }
        else {
            return true;
        }
    }
};
```
## Code Explanation

- The code checks if n is divisible by 4 using the modulo operator %. If n % 4 == 0, it means you cannot win the game if your opponent plays optimally.  
- Otherwise, you can always force a win by choosing a move that leaves a multiple of 4 for your opponent.  

## Complexity Analysis  

- Time Complexity: O(1), as it only requires a simple arithmetic check.  
- Space Complexity: O(1), as no additional memory is used apart from a few variables.

## Additional Notes

This problem is a great example of how mathematical insight can lead to an optimal and constant-time solution. It introduces concepts of game theory and modularity in problem-solving.