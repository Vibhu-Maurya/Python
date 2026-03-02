# Two Sum Problem

## Problem Statement

Given an array of integers `nums` and an integer `target`, return
indices of the two numbers such that they add up to `target`.

-   Each input has exactly one solution.
-   You may not use the same element twice.
-   You can return the answer in any order.

------------------------------------------------------------------------

## Examples

### Example 1

**Input:**\
nums = \[2, 7, 11, 15\]\
target = 9

**Output:**\
\[0, 1\]

**Explanation:**\
nums\[0\] + nums\[1\] = 2 + 7 = 9

------------------------------------------------------------------------

### Example 2

**Input:**\
nums = \[3, 2, 4\]\
target = 6

**Output:**\
\[1, 2\]

------------------------------------------------------------------------

### Example 3

**Input:**\
nums = \[3, 3\]\
target = 6

**Output:**\
\[0, 1\]

------------------------------------------------------------------------

## Constraints

-   2 ≤ nums.length ≤ 10\^4\
-   -10\^9 ≤ nums\[i\] ≤ 10\^9\
-   -10\^9 ≤ target ≤ 10\^9\
-   Only one valid answer exists

------------------------------------------------------------------------

## Approach 1: Brute Force (Not Optimal)

Check every pair.

### Time Complexity:

O(n²)

------------------------------------------------------------------------

## Approach 2: Hash Map (Optimal Solution)

Use a dictionary to store numbers and their indices.

### Idea

For each element: 1. Compute `complement = target - nums[i]` 2. If
complement exists in dictionary → return indices 3. Otherwise store
current number and index

------------------------------------------------------------------------

## Python Implementation (Optimal)

``` python
class Solution:
    def twoSum(self, nums, target):
        hashmap = {}
        
        for i in range(len(nums)):
            complement = target - nums[i]
            
            if complement in hashmap:
                return [hashmap[complement], i]
            
            hashmap[nums[i]] = i
```

------------------------------------------------------------------------

## Complexity Analysis

-   Time Complexity: O(n)
-   Space Complexity: O(n)

------------------------------------------------------------------------

## Key Points

-   Hash map reduces time from O(n²) to O(n).
-   Store value → index mapping.
-   Always check complement before inserting current element.
