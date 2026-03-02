# Maximum Subarray Sum (Kadane's Algorithm)

## Problem Statement

You are given an integer array `arr[]`.\
Find the **maximum sum of a subarray** (containing at least one
element).

> A subarray is a continuous part of an array.

------------------------------------------------------------------------

## Examples

### Example 1

**Input:**\
arr = \[2, 3, -8, 7, -1, 2, 3\]

**Output:**\
11

**Explanation:**\
The subarray `[7, -1, 2, 3]` has the largest sum = 11.

------------------------------------------------------------------------

### Example 2

**Input:**\
arr = \[-2, -4\]

**Output:**\
-2

**Explanation:**\
The subarray `[-2]` has the largest sum = -2.

------------------------------------------------------------------------

### Example 3

**Input:**\
arr = \[5, 4, 1, 7, 8\]

**Output:**\
25

**Explanation:**\
The subarray `[5, 4, 1, 7, 8]` has the largest sum = 25.

------------------------------------------------------------------------

## Constraints

-   1 ≤ arr.size() ≤ 10\^5\
-   -10\^4 ≤ arr\[i\] ≤ 10\^4

------------------------------------------------------------------------

## Approach: Kadane's Algorithm (Optimal Solution)

### Idea:

1.  Keep track of:
    -   `current_sum`
    -   `max_sum`
2.  Traverse the array:
    -   Add current element to `current_sum`
    -   Update `max_sum`
    -   If `current_sum` becomes negative, reset it to 0

------------------------------------------------------------------------

## Python Implementation

``` python
class Solution:
    def maxSubArraySum(self, arr):
        current_sum = arr[0]
        max_sum = arr[0]
        
        for i in range(1, len(arr)):
            current_sum = max(arr[i], current_sum + arr[i])
            max_sum = max(max_sum, current_sum)
        
        return max_sum
```

------------------------------------------------------------------------

## Complexity Analysis

-   Time Complexity: O(n)
-   Space Complexity: O(1)

------------------------------------------------------------------------

## Key Points

-   This is known as Kadane's Algorithm.
-   Works even when all elements are negative.
-   Only one traversal is required.

## screenshot 
<img width="1913" height="927" alt="image" src="https://github.com/user-attachments/assets/6b05f9b5-7246-4d8a-ada3-b1f9906337fa" />

