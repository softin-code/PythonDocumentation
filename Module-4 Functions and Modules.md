Absolutely! Here's a complete guide to **Python Functions and Modules** with **examples** for each topic:

---

## 🔹 **1. Defining and Calling Functions**

```python
def greet():
    print("Hello, Python learner!")

greet()  # Call the function
```

---

## 🔹 **2. Function Parameters and Return Values**

### Parameters and Return

```python
def add(a, b):
    return a + b

result = add(3, 5)
print(result)  # 8
```

---

## 🔹 **3. Parameters**

### Positional Parameters:

```python
def greet(name, message):
    print(f"{message}, {name}!")

greet("Alice", "Good morning")
```

### Default Parameters:

```python
def greet(name="User"):
    print(f"Hello, {name}!")

greet()
greet("Alice")
```

---

## 🔹 **4. Different Kinds of Arguments**

### Keyword Arguments:

```python
def greet(name, age):
    print(f"{name} is {age} years old.")

greet(age=25, name="Bob")
```

### Variable-Length Arguments (`*args`, `**kwargs`):

```python
def sum_all(*args):
    print(sum(args))

sum_all(1, 2, 3, 4)  # 10

def show_details(**kwargs):
    for key, value in kwargs.items():
        print(f"{key} = {value}")

show_details(name="Alice", age=30)
```

---

## 🔹 **5. Scope and Lifetime of Variables**

### Local vs Global Scope

```python
x = 10  # Global

def show():
    x = 5  # Local
    print("Inside function:", x)

show()
print("Outside function:", x)
```

### Using `global` keyword:

```python
count = 0

def increase():
    global count
    count += 1

increase()
print(count)  # 1
```

---

## 🔹 **6. Introduction to Modules and Libraries**

### Importing Standard Modules:

```python
import math

print(math.sqrt(16))     # 4.0
print(math.pi)           # 3.14159...
```

### Importing specific functions:

```python
from random import randint

print(randint(1, 10))  # Random number between 1 and 10
```

### Creating Your Own Module:

1. Create `my_module.py`:
```python
def hello(name):
    return f"Hello, {name}!"
```

2. Use it in another file:
```python
import my_module

print(my_module.hello("Alice"))
```

---

## 🧩 **7. Problem-Solving Session**

### ✅ Problem 1: Factorial Function

```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(5))  # 120
```

---

### ✅ Problem 2: Check Prime Number

```python
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5)+1):
        if n % i == 0:
            return False
    return True

print(is_prime(7))  # True
```

---

### ✅ Problem 3: Calculator with `*args`

```python
def calculator(op, *args):
    if op == "add":
        return sum(args)
    elif op == "mul":
        result = 1
        for n in args:
            result *= n
        return result

print(calculator("add", 1, 2, 3))  # 6
print(calculator("mul", 2, 3, 4))  # 24
```

---

## ❓ **8. Q&A Session — Common Questions**

### 🔸 Q: Can a function return multiple values?
```python
def stats(a, b):
    return a + b, a * b

s, p = stats(2, 3)
print(s, p)  # 5 6
```

---

### 🔸 Q: Can functions be passed as arguments?
```python
def greet(name):
    return f"Hello, {name}"

def call_func(func, name):
    return func(name)

print(call_func(greet, "Alice"))
```

---

### 🔸 Q: What is a lambda function?
```python
square = lambda x: x * x
print(square(5))  # 25
```

---

Let me know if you want a **practice quiz**, or if you'd like to solve problems with hints, or go deeper into advanced function topics like decorators or closures.