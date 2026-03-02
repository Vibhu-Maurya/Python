# Kth Smallest Element in an Array

## Problem Statement

Given an integer array `arr[]` and an integer `k`, your task is to find
and return the **kth smallest element** in the given array.

> The kth smallest element is determined based on the sorted order of
> the array.

------------------------------------------------------------------------

## Examples

### Example 1

**Input:** arr = \[10, 5, 4, 3, 48, 6, 2, 33, 53, 10\], k = 4

**Output:** 5

**Explanation:** After sorting → \[2, 3, 4, 5, 6, 10, 10, 33, 48, 53\]\
The 4th smallest element is **5**.

------------------------------------------------------------------------

### Example 2

**Input:** arr = \[7, 10, 4, 3, 20, 15\], k = 3

**Output:** 7

**Explanation:** After sorting → \[3, 4, 7, 10, 15, 20\]\
The 3rd smallest element is **7**.

------------------------------------------------------------------------

## Constraints

-   1 ≤ arr.size() ≤ 10\^5\
-   1 ≤ arr\[i\] ≤ 10\^5\
-   1 ≤ k ≤ arr.size()

------------------------------------------------------------------------

## Approach 1: Sorting (Simple Method)

1.  Sort the array.
2.  Return element at index `k - 1`.

### Python Implementation

``` python
class Solution:
    def kthSmallest(self, arr, k):
        arr.sort()
        return arr[k - 1]
```

### Complexity

-   Time Complexity: O(n log n)
-   Space Complexity: O(1) (if in-place sort)

------------------------------------------------------------------------

## Approach 2: Using Min Heap (Efficient for Large Data)

``` python
import heapq

class Solution:
    def kthSmallest(self, arr, k):
        heapq.heapify(arr)
        for _ in range(k - 1):
            heapq.heappop(arr)
        return heapq.heappop(arr)
```

### Complexity

-   Time Complexity: O(n + k log n)
-   Space Complexity: O(1)

------------------------------------------------------------------------

## Key Points

-   Sorting is the easiest solution.
-   Heap is better when k is small compared to n.
-   Always return `arr[k - 1]` after sorting (since indexing starts from
    0).
---------------------------------------------------------------------------
## Screenshot
<img width="1913" height="912" alt="image" src="https://github.com/user-attachments/assets/0f7e01fc-faf4-4027-8ae1-7d29aecbb459" />

