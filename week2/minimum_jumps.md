# 🚀 Minimum Number of Jumps (Greedy Approach)

## 🧠 Problem Statement

You are given an array `arr[]` of non-negative numbers. Each number represents the **maximum number of steps** you can jump forward from that position.

- If `arr[i] = 3`, you can jump to `i+1`, `i+2`, or `i+3`
- If `arr[i] = 0`, you cannot move forward from that position

### 🎯 Goal
Find the **minimum number of jumps** required to reach the last index.

> Return `-1` if it is not possible to reach the end.

---

## 🧪 Example

### ✅ Input
```
arr = [1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9]
```

### ✅ Output
```
3
```

### 💡 Explanation
- Jump from index 0 → index 1
- Jump from index 1 → index 4
- Jump from index 4 → last index

---

## 🚀 Approach: Greedy Algorithm

### 💡 Idea

- Track:
  - `maxReach` → farthest index reachable
  - `steps` → steps we can still take
  - `jumps` → number of jumps

- Traverse the array:
  - Update `maxReach`
  - Decrease `steps`
  - When `steps == 0`, increase `jumps`

---

## 🧾 Python Implementation

```python
class Solution:
    def minJumps(self, arr):
        n = len(arr)

        if n <= 1:
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

## ⏱️ Complexity Analysis

- Time Complexity: **O(n)**
- Space Complexity: **O(1)**

---

## 🔥 Key Points

- Greedy approach is optimal
- Always jump to the farthest reachable position
- Handles unreachable cases

---

## 📚 Summary

This is a classic greedy problem often asked in interviews.  
Efficient solution avoids recursion and dynamic programming.

---
