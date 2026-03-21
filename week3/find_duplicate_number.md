# 🔁 Find the Duplicate Number

## 🧩 Problem Statement
Given an array `nums` containing `n + 1` integers where each integer is in the range `[1, n]`, return the duplicate number.

### ⚠️ Constraints
- Do NOT modify the array
- Use only constant extra space
- Must run in O(n) time

---

## ✅ Examples

### Example 1
```
nums = [1,3,4,2,2]
```
Output:
```
2
```

### Example 2
```
nums = [3,1,3,4,2]
```
Output:
```
3
```

### Example 3
```
nums = [3,3,3,3,3]
```
Output:
```
3
```

---

## 🚀 Optimal Approach: Floyd’s Cycle Detection

### 💡 Idea
Treat array like a linked list:
- Index → node
- Value → next pointer

Duplicate creates a cycle → detect it.

---

## 🧑‍💻 Code

```python
class Solution:
    def findDuplicate(self, nums):
        slow = nums[0]
        fast = nums[0]

        # Step 1: Detect cycle
        while True:
            slow = nums[slow]
            fast = nums[nums[fast]]

            if slow == fast:
                break

        # Step 2: Find entry point
        slow = nums[0]

        while slow != fast:
            slow = nums[slow]
            fast = nums[fast]

        return slow
```

---

## ⏱ Complexity
- Time Complexity: **O(n)**
- Space Complexity: **O(1)**

---

## 🎯 Key Points
- Uses Floyd’s Tortoise & Hare algorithm
- No extra space required
- Does not modify array
- Guaranteed cycle due to duplicate

---

## 📌 Why Duplicate Exists?
Using **Pigeonhole Principle**:
- `n+1` numbers in range `[1, n]`
- At least one number must repeat

---

## ❌ Alternative (Not Allowed)
```python
# Uses extra space
seen = set()
for num in nums:
    if num in seen:
        return num
    seen.add(num)
```

---

## 📌 Conclusion
Cycle detection gives the most efficient and interview-friendly solution for this problem.
