# 🔍 Search Insert Position (Binary Search)

## 🧠 Problem Statement

Given a sorted array of distinct integers and a target value, return the index if the target is found.  
If not, return the index where it would be if it were inserted in order.

> You must write an algorithm with **O(log n)** runtime complexity.

---

## 🧪 Example

### ✅ Example 1

**Input:**
nums = [1,3,5,6]
target = 5

**Output:**
2

---

### ✅ Example 2

**Input:**
nums = [1,3,5,6]
target = 2

**Output:**
1

---

### ✅ Example 3

**Input:**
nums = [1,3,5,6]
target = 7

**Output:**
4

---

## 🚀 Approach: Binary Search

### 💡 Idea

- Use binary search to efficiently locate the target
- If found → return index  
- If not found → return insertion position (`left`)

---

## 🧾 Python Implementation

```python
class Solution:
    def searchInsert(self, nums, target):
        left, right = 0, len(nums) - 1

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

---

## 📊 Complexity Analysis

- Time Complexity: **O(log n)**
- Space Complexity: **O(1)**

---

## 🔥 Key Points

- Binary search reduces time from O(n) → O(log n)
- `left` gives correct insertion position
- Works only on **sorted arrays**

---

## 📚 Summary

This is a classic binary search problem frequently asked in interviews.
