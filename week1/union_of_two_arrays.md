# Union of Two Arrays

## Problem Statement

You are given two arrays `a[]` and `b[]`.\
Your task is to return the **Union** of both arrays in any order.

The Union of two arrays is a collection of all **distinct elements**
present in either of the arrays.

> If an element appears more than once in one or both arrays, it should
> be included only once in the result.\
> The driver code will print the result in sorted order.

------------------------------------------------------------------------

## Examples

### Example 1

**Input:**\
a = \[1, 2, 3, 2, 1\]\
b = \[3, 2, 2, 3, 3, 2\]

**Output:**\
\[1, 2, 3\]

------------------------------------------------------------------------

### Example 2

**Input:**\
a = \[1, 2, 3\]\
b = \[4, 5, 6\]

**Output:**\
\[1, 2, 3, 4, 5, 6\]

------------------------------------------------------------------------

### Example 3

**Input:**\
a = \[1, 2, 1, 1, 2\]\
b = \[2, 2, 1, 2, 1\]

**Output:**\
\[1, 2\]

------------------------------------------------------------------------

## Constraints

-   1 ≤ a.size(), b.size() ≤ 10\^6\
-   0 ≤ a\[i\], b\[i\] ≤ 10\^5

------------------------------------------------------------------------

## Approach 1: Using Set (Most Efficient & Simple)

1.  Convert both arrays into a set to remove duplicates.
2.  Take union using set operation.
3.  Convert back to list and return.

### Python Implementation

``` python
class Solution:
    def findUnion(self, a, b):
        return list(set(a) | set(b))
```

### Complexity

-   Time Complexity: O(n + m)
-   Space Complexity: O(n + m)

------------------------------------------------------------------------

## Approach 2: Manual Method (Without Using Built-in Union)

``` python
class Solution:
    def findUnion(self, a, b):
        result = set()
        
        for num in a:
            result.add(num)
        
        for num in b:
            result.add(num)
        
        return list(result)
```

------------------------------------------------------------------------

## Key Points

-   Union means distinct elements from both arrays.
-   Duplicate elements must appear only once.
-   Order does not matter (driver will sort).
## Screenshot
<img width="1913" height="896" alt="image" src="https://github.com/user-attachments/assets/0144fa1e-7c27-4da5-a5bb-34ec96c6a297" />


