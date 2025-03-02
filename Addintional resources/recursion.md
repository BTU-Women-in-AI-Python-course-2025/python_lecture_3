# **Recursion in Python**
### **What is Recursion?**
Recursion is a technique in which a **function calls itself** to solve a problem in smaller subproblems.

🔹 **Every recursive function must have a base case** (stopping condition) to avoid infinite loops.  
🔹 **Recursive functions are useful for problems like factorials, Fibonacci sequences, and tree traversals.**  

---

## **1. Basic Structure of Recursion**
```python
def recursive_function():
    # Base case (stopping condition)
    if condition:
        return
    # Recursive call
    recursive_function()
```

---

## **2. Example: Factorial Using Recursion**
The **factorial** of a number (n!) is calculated as:  
\[
n! = n \times (n-1) \times (n-2) \times ... \times 1
\]

### **Factorial Without Recursion**
```python
def factorial_iterative(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result

print(factorial_iterative(5))  # Output: 120
```

---

### **Factorial Using Recursion**
```python
def factorial(n):
    if n == 0 or n == 1:  # Base case
        return 1
    return n * factorial(n - 1)  # Recursive call

print(factorial(5))  # Output: 120
```

🔹 **How it works?**
- `factorial(5) = 5 * factorial(4)`
- `factorial(4) = 4 * factorial(3)`
- `factorial(3) = 3 * factorial(2)`
- `factorial(2) = 2 * factorial(1)`
- `factorial(1) = 1` (Base case reached)
- Then the values multiply back up!

---

## **3. Example: Fibonacci Sequence**
The **Fibonacci sequence** follows the pattern:
\[
F(n) = F(n-1) + F(n-2)
\]
with base cases:
\[
F(0) = 0, \quad F(1) = 1
\]

### **Fibonacci Without Recursion**
```python
def fibonacci_iterative(n):
    a, b = 0, 1
    for _ in range(n):
        a, b = b, a + b
    return a

print(fibonacci_iterative(6))  # Output: 8
```

---

### **Fibonacci Using Recursion**
```python
def fibonacci(n):
    if n == 0:  # Base case 1
        return 0
    elif n == 1:  # Base case 2
        return 1
    return fibonacci(n - 1) + fibonacci(n - 2)  # Recursive call

print(fibonacci(6))  # Output: 8
```

🔹 **How it works?**
- `fibonacci(6) = fibonacci(5) + fibonacci(4)`
- `fibonacci(5) = fibonacci(4) + fibonacci(3)`
- ... **Until reaching base cases (`fibonacci(0)` and `fibonacci(1)`)**

⚠ **Note:** The recursive Fibonacci function is inefficient because it recalculates the same values multiple times. It can be optimized using **memoization**.

---

## **4. Recursion vs Iteration**
| Feature | Recursion | Iteration |
|---------|----------|-----------|
| **Definition** | Function calls itself | Uses loops (`for`, `while`) |
| **Base case** | Required to stop recursion | Loop condition controls execution |
| **Memory** | Uses more memory (stack calls) | Uses less memory |
| **Performance** | Slower (due to repeated calls) | Faster |

---

## **5. When to Use Recursion?**
✔ When a problem can be divided into smaller subproblems.  
✔ When using **tree-based structures** (e.g., file system traversal).  
✔ When **backtracking** is required (e.g., solving mazes).  

🚫 Avoid recursion for **simple loops** (like summing numbers) because iteration is more efficient.

---

## **6. Example: Recursive Sum of a List**
```python
def recursive_sum(numbers):
    if not numbers:  # Base case: empty list
        return 0
    return numbers[0] + recursive_sum(numbers[1:])  # Recursive step

print(recursive_sum([1, 2, 3, 4, 5]))  # Output: 15
```

---

## **7. Example: Reverse a String Recursively**
```python
def reverse_string(s):
    if len(s) == 0:  # Base case
        return s
    return s[-1] + reverse_string(s[:-1])  # Recursive call

print(reverse_string("hello"))  # Output: "olleh"
```

---

## **Summary Table**
| Concept | Explanation | Example |
|---------|------------|---------|
| **Recursion** | A function that calls itself | `factorial(n) = n * factorial(n-1)` |
| **Base Case** | The stopping condition | `if n == 1: return 1` |
| **Recursive Case** | Calls itself with a smaller input | `return n * factorial(n - 1)` |
| **Factorial** | `n! = n × (n-1)!` | `factorial(5) → 120` |
| **Fibonacci** | `F(n) = F(n-1) + F(n-2)` | `fibonacci(6) → 8` |
| **Use Cases** | Tree structures, backtracking | File system traversal |
