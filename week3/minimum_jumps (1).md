# 🏃 Minimum Jumps Problem

## 🧩 Problem Statement
Given an array `arr[]` of non-negative numbers where each element represents the maximum number of steps you can jump forward from that position.

Find the **minimum number of jumps** required to reach the last index.

> Return **-1** if it is not possible to reach the end.

---

## ✅ Examples

### Example 1
```
arr = [1, 3, 5, 8, 9]
```
Output:
```
3
```

### Example 2
```
arr = [1, 4, 3, 2, 6, 7]
```
Output:
```
2
```

### Example 3
```
arr = [0, 10, 20]
```
Output:
```
-1
```

---

## 🚀 Approach (Greedy)

### 💡 Idea
- Track:
  - `maxReach` → farthest reachable index
  - `steps` → steps left in current jump
  - `jumps` → total jumps taken

---

## 🧑‍💻 Code

```python
class Solution:
    def minJumps(self, arr):
        n = len(arr)

        if n == 1:
            return 0

        if arr[0] == 0:
            return -1

        maxReach = arr[0]
        steps = arr[0]
        jumps = 1

        for i in range(1, n):
            if i == n - 1:
                return jumps

            maxReach = max(maxReach, i + arr[i])
            steps -= 1

            if steps == 0:
                jumps += 1

                if i >= maxReach:
                    return -1

                steps = maxReach - i

        return -1
```

---

## ⏱ Complexity
- Time Complexity: **O(n)**
- Space Complexity: **O(1)**

---

## 🎯 Key Points
- Use greedy approach
- Track max reachable index
- Handle edge case: `arr[0] == 0`
- Return `-1` if stuck

---

## 📌 Conclusion
This is a classic greedy problem where we expand our reachable range efficiently to minimize jumps.
