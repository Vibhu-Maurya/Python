# 🌧️ Trapping Rain Water

## 🧩 Problem Statement
Given an array `arr[]` of non-negative integers representing the height of blocks, compute how much water can be trapped between them.

---

## ✅ Examples

### Example 1
```
arr = [3, 0, 1, 0, 4, 0, 2]
```
Output:
```
10
```

---

### Example 2
```
arr = [3, 0, 2, 0, 4]
```
Output:
```
7
```

---

### Example 3
```
arr = [1, 2, 3, 4]
```
Output:
```
0
```

---

### Example 4
```
arr = [2, 1, 5, 3, 1, 0, 4]
```
Output:
```
9
```

---

## 🚀 Optimal Approach (Two Pointer)

### 💡 Idea
- Use two pointers (left & right)
- Track:
  - left_max → max height from left
  - right_max → max height from right
- Water trapped = min(left_max, right_max) - height

---

## 🧑‍💻 Code

```python
class Solution:
    def maxWater(self, arr):
        n = len(arr)

        left = 0
        right = n - 1

        left_max = 0
        right_max = 0

        water = 0

        while left <= right:

            if arr[left] <= arr[right]:
                if arr[left] >= left_max:
                    left_max = arr[left]
                else:
                    water += left_max - arr[left]
                left += 1
            else:
                if arr[right] >= right_max:
                    right_max = arr[right]
                else:
                    water += right_max - arr[right]
                right -= 1

        return water
```
<img width="1911" height="904" alt="image" src="https://github.com/user-attachments/assets/ffbe5d1b-f8d0-4f90-af2d-318778933e09" />

---

## ⏱ Complexity
- Time Complexity: **O(n)**
- Space Complexity: **O(1)**

---

## 🎯 Key Points
- Two-pointer technique is optimal
- No extra space required
- Works in single pass

---

## 📌 Conclusion
The two-pointer approach efficiently computes trapped water using left and right boundaries.
