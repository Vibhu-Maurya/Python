# Search Insert Position (Binary Search)

## Problem Statement

Given a **sorted array of distinct integers** `nums[]` and a target
value `target`, return the index if the target is found.

If not found, return the index where it would be inserted in order.

> You must write an algorithm with **O(log n)** runtime complexity.

------------------------------------------------------------------------

## Examples

### Example 1

**Input:**\
nums = \[1, 3, 5, 6\]\
target = 5

**Output:**\
2

------------------------------------------------------------------------

### Example 2

**Input:**\
nums = \[1, 3, 5, 6\]\
target = 2

**Output:**\
1

------------------------------------------------------------------------

### Example 3

**Input:**\
nums = \[1, 3, 5, 6\]\
target = 7

**Output:**\
4

------------------------------------------------------------------------

## Constraints

-   1 ≤ nums.length ≤ 10\^4\
-   -10\^4 ≤ nums\[i\] ≤ 10\^4\
-   nums contains distinct values sorted in ascending order\
-   -10\^4 ≤ target ≤ 10\^4

------------------------------------------------------------------------

## Approach: Binary Search (Optimal Solution)

Since the array is sorted and we need O(log n) time complexity, we use
**Binary Search**.

### Algorithm Steps

1.  Initialize:
    -   `left = 0`
    -   `right = len(nums) - 1`
2.  While `left <= right`:
    -   Find middle index `mid`
    -   If `nums[mid] == target`, return `mid`
    -   If `nums[mid] < target`, search right half
    -   Else search left half
3.  If not found, return `left` (correct insertion position)

------------------------------------------------------------------------

## Python Implementation

``` python
class Solution:
    def searchInsert(self, nums, target):
        left = 0
        right = len(nums) - 1
        
        while left <= right:
            mid = (left + right) // 2
            
            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                left = mid + 1
            else:
                right = mid - 1
        
        return left
```

------------------------------------------------------------------------

## Complexity Analysis

-   Time Complexity: O(log n)
-   Space Complexity: O(1)

------------------------------------------------------------------------
## Screenshot
<img width="1911" height="922" alt="image" src="https://github.com/user-attachments/assets/5eb5df0f-d46c-41c5-a638-26cbe7c357b2" />


## Key Points

-   Binary Search is required for O(log n) complexity.
-   If target is not found, `left` gives correct insertion index.
-   Works for inserting at beginning, middle, or end.
