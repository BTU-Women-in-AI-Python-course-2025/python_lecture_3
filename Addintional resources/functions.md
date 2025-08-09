# **Functions in Python**

Functions are reusable blocks of code that perform a specific task. They help **organize code**, **reduce redundancy**, and **make programs more readable**.

### **1. Defining a Function**

A function is defined using the `def` keyword.

#### **Syntax:**

```python
def function_name():
    # Code to execute
```

#### **Example: A simple function**

```python
def greet():
    print("Hello, Python!")
```

To call the function:

```python
greet()
```

**Output:**

```
Hello, Python!
```

---

## **2. Parameters and Arguments**

* **Parameters**: Variables inside parentheses when defining a function.
* **Arguments**: The actual values passed when calling the function.

### **Example: Function with Parameters**

```python
def greet(name):
    print(f"Hello, {name}!")
```

Calling the function:

```python
greet("Mariam")
```

**Output:**

```
Hello, Mariam!
```

---

## **3. Types of Function Arguments**

Python supports different types of arguments:

### **A) Positional Arguments**

```python
def add(a, b):
    return a + b

print(add(3, 5))  # 8
```

---

### **B) Default Arguments**

```python
def greet(name="Student"):
    print(f"Hello, {name}!")

greet()        # Hello, Student!
greet("Mariam")  # Hello, Mariam!
```

---

### **C) Keyword Arguments**

```python
def info(name, age):
    print(f"Name: {name}, Age: {age}")

info(age=25, name="Mariam")
```

---

### **D) Arbitrary Arguments (`*args`)**

```python
def add_all(*numbers):
    return sum(numbers)

print(add_all(1, 2, 3, 4, 5))  # 15
```

---

### **E) Arbitrary Keyword Arguments (`**kwargs`)**

```python
def student_info(**details):
    for key, value in details.items():
        print(f"{key}: {value}")

student_info(name="Mariam", age=25, course="Python")
```

---

## **4. Return Statement**

```python
def square(num):
    return num * num

print(square(4))  # 16
```

---

## **5. Lambda Functions (Anonymous Functions)**

A **lambda function** is a short, one-line function.

```python
lambda arguments: expression
```

### **Example 1: Lambda Function for Addition**

```python
add = lambda a, b: a + b
print(add(3, 5))  # 8
```

### **Example 2: Using Lambda in `map()`**

```python
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x * x, numbers))
print(squared)  # [1, 4, 9, 16, 25]
```

---

## **6. Functional Helpers in Python**

Python has several built-in functions that work with other functions and iterables, often used with `lambda` for concise data processing.

| Function                                          | Purpose                                   | Example                                 |
| ------------------------------------------------- | ----------------------------------------- | --------------------------------------- |
| **`map(func, iterable)`**                         | Apply `func` to every element             | `map(lambda x: x*2, nums)`              |
| **`filter(func, iterable)`**                      | Keep elements where `func` returns `True` | `filter(lambda x: x>0, nums)`           |
| **`reduce(func, iterable)`** *(from `functools`)* | Reduce to a single value cumulatively     | `reduce(lambda a,b: a+b, nums)`         |
| **`sorted(iterable, key=func)`**                  | Sort using `func` as a key                | `sorted(users, key=lambda u: u['age'])` |
| **`any(iterable)`**                               | `True` if any element is truthy           | `any(nums)`                             |
| **`all(iterable)`**                               | `True` if all elements are truthy         | `all(nums)`                             |
| **`zip(*iterables)`**                             | Combine iterables element-wise            | `zip(names, ages)`                      |
| **`enumerate(iterable)`**                         | Pair each element with an index           | `enumerate(items)`                      |

**Example – Filtering Published Posts:**

```python
posts = [
    {"title": "Post 1", "published": True},
    {"title": "Post 2", "published": False}
]

published_posts = list(filter(lambda p: p["published"], posts))
print(published_posts)
```

**Output:**

```python
[{'title': 'Post 1', 'published': True}]
```

---

## **Summary Table**

| Feature       | Description                     | Example                      |
| ------------- | ------------------------------- | ---------------------------- |
| **Function**  | Block of reusable code          | `def greet(): print("Hi")`   |
| **Parameter** | Variable in function definition | `def add(a, b):`             |
| **Argument**  | Value passed to function        | `add(3, 5)`                  |
| **Return**    | Sends value back                | `return a + b`               |
| **Lambda**    | One-line function               | `lambda x: x*2`              |
| **map**       | Transform data                  | `map(lambda x:x*2, nums)`    |
| **filter**    | Select data                     | `filter(lambda x:x>0, nums)` |

---
