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
- **Parameters**: Variables inside parentheses when defining a function.
- **Arguments**: The actual values passed when calling the function.

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
Values are passed in the order of parameters.
```python
def add(a, b):
    return a + b

print(add(3, 5))
```
**Output:**
```
8
```

---

### **B) Default Arguments**
If no value is passed, a default value is used.
```python
def greet(name="Student"):
    print(f"Hello, {name}!")

greet()        # Uses default value
greet("Mariam")  # Uses provided value
```
**Output:**
```
Hello, Student!
Hello, Mariam!
```

---

### **C) Keyword Arguments**
Arguments are passed by specifying parameter names.
```python
def info(name, age):
    print(f"Name: {name}, Age: {age}")

info(age=25, name="Mariam")
```
**Output:**
```
Name: Mariam, Age: 25
```

---

### **D) Arbitrary Arguments (`*args`)**
Used when we don’t know the number of arguments.
```python
def add_all(*numbers):
    return sum(numbers)

print(add_all(1, 2, 3, 4, 5))  # Accepts multiple arguments
```
**Output:**
```
15
```

---

### **E) Arbitrary Keyword Arguments (`**kwargs`)**
Used when passing a dictionary of named arguments.
```python
def student_info(**details):
    for key, value in details.items():
        print(f"{key}: {value}")

student_info(name="Mariam", age=25, course="Python")
```
**Output:**
```
name: Mariam
age: 25
course: Python
```

---

## **4. Return Statement**
A function can return a value using `return`.

```python
def square(num):
    return num * num

result = square(4)
print(result)
```
**Output:**
```
16
```

---

## **5. Lambda Functions (Anonymous Functions)**
A **lambda function** is a short, one-line function.

### **Syntax:**
```python
lambda arguments: expression
```

### **Example 1: Lambda Function for Addition**
```python
add = lambda a, b: a + b
print(add(3, 5))
```
**Output:**
```
8
```

### **Example 2: Using Lambda in `map()`**
```python
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x * x, numbers))
print(squared)
```
**Output:**
```
[1, 4, 9, 16, 25]
```

---

## **Summary Table**
| Feature | Description | Example |
|----------|------------|---------|
| **Function** | Block of reusable code | `def greet(): print("Hello")` |
| **Parameter** | Variable in function definition | `def add(a, b):` |
| **Argument** | Value passed to function | `add(3, 5)` |
| **Return** | Sends value back from function | `return a + b` |
| **Lambda** | One-line function | `lambda x: x * 2` |
