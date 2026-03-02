# Find the Largest Element in an Array

## Problem Statement

Given an array `arr[]`, the task is to find and return the **largest
element** in the array.

------------------------------------------------------------------------

## Example

### Input:

arr = \[1, 8, 7, 56, 90\]

### Output:

90

### Explanation:

The largest element in the array is `90`.

------------------------------------------------------------------------

## Approach

1.  Assume the first element as the largest.
2.  Traverse the array.
3.  If any element is greater than the current maximum, update it.
4.  Return the maximum value.

------------------------------------------------------------------------

## Python Implementation

``` python
class Solution:
    def largest(self, arr):
        maximum = arr[0]
        
        for num in arr:
            if num > maximum:
                maximum = num
        
        return maximum
```

------------------------------------------------------------------------

## Complexity Analysis

-   Time Complexity: O(n)
-   Space Complexity: O(1)

------------------------------------------------------------------------
## Screenshot
<img width="1910" height="916" alt="image" src="https://github.com/user-attachments/assets/22776d46-852e-45e2-bc5f-e4b945cddfa5" />


## Key Points

-   Only one traversal is required.
-   No extra space is used.
-   Efficient for large arrays.
