# 🔀 Merge Without Extra Space

## 🧩 Problem Statement
Given two sorted arrays `a[]` and `b[]` of size `n` and `m`, merge them in sorted order **without using extra space**.

After merging:
- `a[]` should contain first `n` smallest elements
- `b[]` should contain remaining `m` elements

---

## ✅ Examples

### Example 1
```
a = [2, 4, 7, 10]
b = [2, 3]
```
Output:
```
a = [2, 2, 3, 4]
b = [7, 10]
```

---

### Example 2
```
a = [1, 5, 9, 10, 15, 20]
b = [2, 3, 8, 13]
```
Output:
```
a = [1, 2, 3, 5, 8, 9]
b = [10, 13, 15, 20]
```

---

## 🚀 Optimal Approach: Gap Method (Shell Sort Idea)

### 💡 Idea
- Treat both arrays as a single array
- Use a decreasing gap
- Compare elements at distance `gap` and swap if needed

---

## 🧑‍💻 Code

```python
class Solution:
    def merge(self, a, b, n, m):
        def nextGap(gap):
            if gap <= 1:
                return 0
            return (gap // 2) + (gap % 2)

        gap = n + m

        while gap > 0:
            gap = nextGap(gap)

            i = 0
            while i + gap < n + m:
                j = i + gap

                if i < n and j < n:
                    if a[i] > a[j]:
                        a[i], a[j] = a[j], a[i]

                elif i < n and j >= n:
                    if a[i] > b[j - n]:
                        a[i], b[j - n] = b[j - n], a[i]

                else:
                    if b[i - n] > b[j - n]:
                        b[i - n], b[j - n] = b[j - n], b[i - n]

                i += 1
```

---

## ⏱ Complexity
- Time: **O((n+m) log(n+m))**
- Space: **O(1)**

---

## 🎯 Key Points
- No extra space used
- Based on Shell Sort (gap method)
- Works in-place

---

## 📌 Conclusion
Gap method is the most efficient way to merge two sorted arrays without using extra space.
