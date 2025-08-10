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


**1) `map(func, iterable)`** – Transform each element

```python
numbers = [1, 2, 3, 4]
doubled = list(map(lambda x: x * 2, numbers))
print(doubled)  # [2, 4, 6, 8]
```

---

**2) `filter(func, iterable)`** – Keep only matching elements

```python
numbers = [-3, -1, 0, 2, 5]
positive_nums = list(filter(lambda x: x > 0, numbers))
print(positive_nums)  # [2, 5]
```

---

**3) `reduce(func, iterable)`** – Combine into one value

*(Needs to be imported from `functools`)*

```python
from functools import reduce

numbers = [1, 2, 3, 4]
total = reduce(lambda a, b: a + b, numbers)
print(total)  # 10
```

---

**4) `sorted(iterable, key=func)`** – Sort items

**Ascending order:**

```python
users = [
    {"name": "Alice", "age": 34},
    {"name": "Bob", "age": 28}
]
sorted_users_asc = sorted(users, key=lambda u: u["age"])
print(sorted_users_asc)
# [{'name': 'Bob', 'age': 28}, {'name': 'Alice', 'age': 34}]
```

**Descending order:**

```python
sorted_users_desc = sorted(users, key=lambda u: u["age"], reverse=True)
print(sorted_users_desc)
# [{'name': 'Alice', 'age': 34}, {'name': 'Bob', 'age': 28}]
```

---

**5) `any(iterable)`** – Check if at least one is truthy

```python
nums = [0, 0, 3]
print(any(nums))  # True (because 3 is truthy)
```

---

**6) `all(iterable)`** – Check if all are truthy

```python
nums = [1, 2, 3]
print(all(nums))  # True (all non-zero)
```

---

**7) `zip(*iterables)`** – Combine iterables element-wise

```python
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]

combined = list(zip(names, ages))
print(combined)
# [('Alice', 25), ('Bob', 30), ('Charlie', 35)]
```

```python
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
cities = ["New York", "London", "Paris"]

combined = list(zip(names, ages, cities))
print(combined)
```
---

**8) `enumerate(iterable)`** – Add index to elements

```python
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits, start=1):
    print(index, fruit)

# 1 apple
# 2 banana
# 3 cherry
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
