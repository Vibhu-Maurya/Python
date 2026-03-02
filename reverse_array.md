# Reverse an Array (In-Place)

## Problem Statement

You are given an array of integers `arr[]`.\
Your task is to reverse the given array.

**Note:** Modify the array in place.

------------------------------------------------------------------------

## Example

### Input:

arr = \[1, 4, 3, 2, 6, 5\]

### Output:

\[5, 6, 2, 3, 4, 1\]

### Explanation:

The first element moves to the last position, the second element moves
to the second last position, and so on.

------------------------------------------------------------------------

## Approach (Two-Pointer Technique)

1.  Initialize two pointers:

    -   `left = 0`
    -   `right = len(arr) - 1`

2.  Swap elements at `left` and `right`.

3.  Move pointers inward:

    -   `left += 1`
    -   `right -= 1`

4.  Continue until `left < right`.

------------------------------------------------------------------------

## Python Implementation

``` python
class Solution:
    def reverseArray(self, arr):
        left = 0
        right = len(arr) - 1
        
        while left < right:
            arr[left], arr[right] = arr[right], arr[left]
            left += 1
            right -= 1
```

------------------------------------------------------------------------

## Complexity

-   Time Complexity: O(n)
-   Space Complexity: O(1)
-------------------------------------------------------------------------
## Screenshot 

 <img width="1898" height="916" alt="Screenshot 2026-03-02 103110" src="https://github.com/user-attachments/assets/2a7beb2f-ac4f-4d47-b336-1fbf17d39507" />
