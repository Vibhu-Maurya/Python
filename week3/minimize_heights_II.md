# 📉 Minimize the Heights II

## 🧩 Problem Statement
Given an array `arr[]` representing heights of towers and an integer `k`, modify each tower by either:
- Increasing height by `k`, OR
- Decreasing height by `k`

Find the minimum possible difference between the tallest and shortest towers.

> ⚠️ Each tower must be modified exactly once  
> ⚠️ No height should become negative  

---

## ✅ Example

### Input
```
arr = [1, 5, 8, 10]
k = 2
```

### Output
```
5
```

### Explanation
Modified array → `[3, 3, 6, 8]`  
Difference → `8 - 3 = 5`

---

## 🚀 Approach (Greedy + Sorting)

### 💡 Idea
- Sort the array
- Try to minimize difference using:
  - Increase smaller values
  - Decrease larger values

---

## 🧑‍💻 Code

```python
class Solution:
    def getMinDiff(self, arr, k):
        n = len(arr)
        arr.sort()
        
        ans = arr[n-1] - arr[0]
        
        smallest = arr[0] + k
        largest = arr[n-1] - k
        
        for i in range(n - 1):
            mini = min(smallest, arr[i+1] - k)
            maxi = max(largest, arr[i] + k)
            
            if mini < 0:
                continue
            
            ans = min(ans, maxi - mini)
        
        return ans
```

---

## ⏱ Complexity
- Time Complexity: **O(n log n)**
- Space Complexity: **O(1)**

---

## 🎯 Key Points
- Sorting is required
- Greedy approach works best
- Avoid negative heights
- Try all partition points

---
<img width="1915" height="922" alt="image" src="https://github.com/user-attachments/assets/436b35b2-54de-4d20-9ad7-b10c8a8f6553" />


## 📌 Conclusion
This is a classic greedy problem where sorting + smart partitioning gives the optimal solution.
