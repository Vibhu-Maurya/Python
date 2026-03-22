# 🔗 Merge Intervals

## 🧩 Problem Statement
Given an array of intervals where `intervals[i] = [start, end]`, merge all overlapping intervals and return the result.

---

## ✅ Examples

### Example 1
```
intervals = [[1,3],[2,6],[8,10],[15,18]]
```
Output:
```
[[1,6],[8,10],[15,18]]
```

---

### Example 2
```
intervals = [[1,4],[4,5]]
```
Output:
```
[[1,5]]
```

---

### Example 3
```
intervals = [[4,7],[1,4]]
```
Output:
```
[[1,7]]
```

---

## 🚀 Approach

### 💡 Idea
1. Sort intervals based on start time
2. Compare current interval with last merged interval
3. If overlapping → merge
4. Else → add new interval

---

## 🧑‍💻 Code

```python
class Solution:
    def merge(self, intervals):
        intervals.sort()

        merged = []

        for interval in intervals:
            if not merged or merged[-1][1] < interval[0]:
                merged.append(interval)
            else:
                merged[-1][1] = max(merged[-1][1], interval[1])

        return merged
```

---

## ⏱ Complexity
- Time Complexity: **O(n log n)** (sorting)
- Space Complexity: **O(n)**

---

## 🎯 Key Points
- Always sort intervals first
- Compare with last merged interval
- Overlapping condition:
  ```
  prev_end >= current_start
  ```

---

## 📌 Conclusion
Sorting + merging gives the optimal solution for interval problems.
