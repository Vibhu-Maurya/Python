# Kth Smallest Element in an Array

## 🧩 Problem Statement
Given an integer array `arr[]` and an integer `k`, find the **kth smallest element** in the array.

---

## ✅ Solution (Sorting Method)

### 💡 Approach
- Sort the array
- Return element at index `k - 1`

### 🧑‍💻 Code
```python
class Solution:
    def kthSmallest(self, arr, k):
        arr.sort()
        return arr[k - 1]
```

---

## 📊 Complexity
- Time Complexity: **O(n log n)**
- Space Complexity: **O(1)**

---

## 🖼️ Output Screenshot
![Result](kth_smallest_output.png)

---

## 🎯 Result
- Test Cases Passed: **1121 / 1121**
- Accuracy: **100%**
- Time Taken: **0.3 sec**

---

## 📌 Conclusion
This is the simplest and most reliable solution for exams and assignments.
