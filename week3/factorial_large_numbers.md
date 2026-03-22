# 🔢 Factorial of Large Numbers

## 🧩 Problem Statement
Given an integer `n`, find its factorial.  
Return a list of integers representing the digits of `n!`.

---

## ✅ Examples

### Example 1
```
n = 5
```
Output:
```
[1, 2, 0]
```

---

### Example 2
```
n = 10
```
Output:
```
[3, 6, 2, 8, 8, 0, 0]
```

---

### Example 3
```
n = 1
```
Output:
```
[1]
```

---

## 🚀 Approach (Using List for Large Numbers)

### 💡 Idea
- Use a list to store digits of factorial
- Multiply numbers from `2` to `n`
- Handle carry manually (like multiplication)

---

## 🧑‍💻 Code

```python
class Solution:
    def factorial(self, n):
        result = [1]

        for i in range(2, n + 1):
            carry = 0

            for j in range(len(result)):
                prod = result[j] * i + carry
                result[j] = prod % 10
                carry = prod // 10

            while carry:
                result.append(carry % 10)
                carry //= 10

        return result[::-1]
```

---

## ⏱ Complexity
- Time Complexity: **O(n²)**
- Space Complexity: **O(n)**

---

## 🎯 Key Points
- Cannot use normal integer for large factorials
- Store digits in list
- Reverse at the end
- Handle carry properly

---

## 📌 Conclusion
Using list-based multiplication helps compute very large factorials efficiently.
