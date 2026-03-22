# 📦 Array Subset (GFG Final Accepted)

## 🧩 Problem Statement
Given two arrays `a[]` and `b[]`, determine whether `b[]` is a subset of `a[]`.

---

## ✅ Examples

### Example 1
```
a = [11, 7, 1, 13, 21, 3, 7, 3]
b = [11, 3, 7, 1, 7]
```
Output:
```
true
```

---

### Example 2
```
a = [1, 2, 3, 4, 4, 5, 6]
b = [1, 2, 4]
```
Output:
```
true
```

---

### Example 3
```
a = [10, 5, 2, 23, 19]
b = [19, 5, 3]
```
Output:
```
false
```

---

## 🚀 Optimal Approach (Sorting + Two Pointers)

### 💡 Idea
- Sort both arrays
- Traverse using two pointers
- Match elements of `b` in `a`

---

## 🧑‍💻 Final Code (GFG Accepted)

```python
class Solution:
    def isSubset(self, a, b):
        a.sort()
        b.sort()

        i = j = 0
        n = len(a)
        m = len(b)

        while i < n and j < m:
            if a[i] < b[j]:
                i += 1
            elif a[i] == b[j]:
                i += 1
                j += 1
            else:
                return False

        return j == m
```
<img width="1911" height="915" alt="image" src="https://github.com/user-attachments/assets/05215ea1-12bf-46ae-9850-ebfb82226592" />


---

## ⏱ Complexity
- Time Complexity: **O(n log n + m log m)**
- Space Complexity: **O(1)**

---

## 🎯 Key Points
- Works for duplicates
- No extra space required
- GFG-safe (handles multiple test cases)
- Return type must be **boolean (True/False)**

---

## 📌 Conclusion
Sorting + two pointers is the most stable and reliable approach for this problem on GFG.
