# Rotate Array by One Position (Clockwise)

## Problem Statement

Given an array `arr[]`, rotate the array by one position in **clockwise
direction**.

Clockwise rotation means: - The last element moves to the front. - All
other elements shift one position to the right.

------------------------------------------------------------------------

## Example

### Input:

arr = \[1, 2, 3, 4, 5\]

### Output:

\[5, 1, 2, 3, 4\]

### Explanation:

After rotating clockwise: - 5 comes to the front. - 1, 2, 3, 4 shift one
position to the right.

------------------------------------------------------------------------

## Approach

1.  Store the last element.
2.  Shift all elements one position to the right.
3.  Place the stored last element at index 0.

------------------------------------------------------------------------

## Python Implementation

``` python
class Solution:
    def rotate(self, arr):
        n = len(arr)
        
        if n == 0:
            return arr
        
        last = arr[n - 1]
        
        for i in range(n - 1, 0, -1):
            arr[i] = arr[i - 1]
        
        arr[0] = last
        
        return arr
```

------------------------------------------------------------------------

## Complexity Analysis

-   Time Complexity: O(n)
-   Space Complexity: O(1)

------------------------------------------------------------------------

## Key Points

-   Rotation is done in-place.
-   No extra array is used.
-   Efficient for large arrays.
