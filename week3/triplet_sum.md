# 🔺 Triplet Sum in Array

## 🧩 Problem Statement
Given an array `arr[]` and an integer `target`, determine if there exists a triplet in the array whose sum equals the target.

Return **true** if such a triplet exists, otherwise **false**.

---

## ✅ Examples

### Example 1
```
arr = [1, 4, 45, 6, 10, 8]
target = 13
```
Output:
```
true
```

---

### Example 2
```
arr = [1, 2, 4, 3, 6, 7]
target = 10
```
Output:
```
true
```

---

### Example 3
```
arr = [40, 20, 10, 3, 6, 7]
target = 24
```
Output:
```
false
```

---

## 🚀 Optimal Approach (Sorting + Two Pointers)

### 💡 Idea
1. Sort the array
2. Fix one element
3. Use two pointers to find remaining sum

---

## 🧑‍💻 Code

```python
class Solution:
    def find3Numbers(self, arr, target):
        arr.sort()
        n = len(arr)

        for i in range(n - 2):
            left = i + 1
            right = n - 1

            while left < right:
                curr_sum = arr[i] + arr[left] + arr[right]

                if curr_sum == target:
                    return True
                elif curr_sum < target:
                    left += 1
                else:
                    right -= 1

        return False
```

---

## ⏱ Complexity
- Time Complexity: **O(n²)**
- Space Complexity: **O(1)**

---

## 🎯 Key Points
- Sorting is necessary
- Two-pointer technique reduces complexity
- Avoid brute force O(n³)

---

## 📌 Conclusion
Sorting + two pointers is the most efficient approach for triplet sum problems.
