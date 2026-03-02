# Find Minimum and Maximum in an Array

## Problem Statement

Given an array `arr[]`, your task is to find the minimum and maximum
elements in the array.

------------------------------------------------------------------------

## Example

### Input:

arr = \[1, 4, 3, 5, 8, 6\]

### Output:

\[1, 8\]

### Explanation:

The minimum element in the array is `1` and the maximum element is `8`.

------------------------------------------------------------------------

## Approach

1.  Assume the first element as both minimum and maximum.
2.  Traverse the array once.
3.  Update:
    -   `minimum` if a smaller element is found.
    -   `maximum` if a larger element is found.
4.  Return `[minimum, maximum]`.

------------------------------------------------------------------------

## Python Implementation

``` python
class Solution:
    def getMinMax(self, arr):
        minimum = arr[0]
        maximum = arr[0]
        
        for num in arr:
            if num < minimum:
                minimum = num
            if num > maximum:
                maximum = num
        
        return [minimum, maximum]
```

------------------------------------------------------------------------

## Complexity Analysis

-   Time Complexity: O(n)
-   Space Complexity: O(1)

------------------------------------------------------------------------

## Key Points

-   Only one traversal is required.
-   No extra space is used.
-   Efficient for large arrays.
