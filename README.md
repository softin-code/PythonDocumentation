Here’s a comprehensive list of **Python syntax** with examples and descriptions, organized by category:

---

### **1. Variables and Data Types**
#### **Variable Assignment**
```python
x = 10           # Integer
name = "Alice"   # String
is_valid = True  # Boolean
pi = 3.14        # Float
```
- No explicit type declaration; dynamic typing.

---

### **2. Basic Operators**
#### **Arithmetic Operators**
```python
print(10 + 3)   # 13 (Addition)
print(10 - 3)   # 7  (Subtraction)
print(10 * 3)   # 30 (Multiplication)
print(10 ** 3)  # 1000 (Exponentiation)
print(10 / 3)   # 3.333... (Division)
print(10 // 3)  # 3 (Floor Division)
print(10 % 3)   # 1 (Modulus)
```

#### **Comparison Operators**
```python
a == b   # Equal to
a != b   # Not equal to
a > b    # Greater than
a <= b   # Less than or equal to
```

#### **Logical Operators**
```python
x and y   # True if both are True
x or y    # True if at least one is True
not x     # Inverts the boolean
```

---

### **3. Control Flow**
#### **Conditional Statements (`if`, `elif`, `else`)**
```python
if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

#### **Loops**
- **`for` Loop**:
  ```python
  for i in range(5):  # Iterates 0-4
      print(i)
  ```
- **`while` Loop**:
  ```python
  while x > 0:
      print(x)
      x -= 1
  ```
- **`break`/`continue`/`else` in Loops**:
  ```python
  for num in [1, 2, 3]:
      if num == 2:
          continue  # Skip iteration
      print(num)
  else:
      print("Loop finished")  # Executes if loop completes normally
  ```

---

### **4. Functions**
#### **Function Definition**
```python
def greet(name="World"):
    return f"Hello, {name}!"
```

#### **Lambda Functions**
```python
square = lambda x: x ** 2
print(square(3))  # 9
```

#### **\*args and \*\*kwargs**
```python
def sum_all(*args):
    return sum(args)
sum_all(1, 2, 3)  # 6
```

---

### **5. Data Structures**
#### **Lists**
```python
numbers = [1, 2, 3]
numbers.append(4)      # [1, 2, 3, 4]
numbers[0] = 10       # [10, 2, 3, 4]
```

#### **Tuples**
```python
point = (3, 4)  # Immutable
x, y = point    # Unpacking
```

#### **Dictionaries**
```python
person = {"name": "Alice", "age": 30}
person["email"] = "alice@example.com"  # Add key-value pair
```

#### **Sets**
```python
primes = {2, 3, 5, 7}
primes.add(11)  # {2, 3, 5, 7, 11}
```

---

### **6. String Operations**
#### **String Formatting (f-Strings)**
```python
name = "Bob"
print(f"Hello, {name}!")  # Hello, Bob!
```

#### **Slicing**
```python
text = "Python"
print(text[1:4])  # "yth" (indices 1 to 3)
```

---

### **7. Error Handling**
#### **`try`/`except`**
```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
```

---

### **8. Object-Oriented Programming (OOP)**
#### **Class Definition**
```python
class Dog:
    def __init__(self, name):
        self.name = name
    
    def bark(self):
        print("Woof!")

dog = Dog("Buddy")
dog.bark()  # Woof!
```

#### **Inheritance**
```python
class GoldenRetriever(Dog):
    def bark(self):
        super().bark()  # Call parent method
        print("Playful bark!")
```

---

### **9. File Handling**
#### **Reading/Writing Files**
```python
with open("file.txt", "r") as file:
    content = file.read()
```

---

### **10. Advanced Features**
#### **List Comprehensions**
```python
squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]
```

#### **Generators**
```python
def count_up_to(n):
    i = 0
    while i <= n:
        yield i
        i += 1

for num in count_up_to(3):
    print(num)  # 0, 1, 2, 3
```

#### **Decorators**
```python
def logger(func):
    def wrapper(*args):
        print(f"Calling {func.__name__}")
        return func(*args)
    return wrapper

@logger
def add(a, b):
    return a + b
```

---

### **11. Walrus Operator (`:=`)**
```python
while (line := input("Enter text: ")) != "quit":
    print(f"You entered: {line}")
```

---

### **12. Asynchronous Programming**
#### **`async`/`await`**
```python
async def fetch_data():
    await some_async_function()
```

---

### **13. Type Hints**
```python
def add(a: int, b: int) -> int:
    return a + b
```

---

### **14. Special Keywords**
- `global`: Modify global variables in a function.
- `nonlocal`: Modify variables in nested functions.
- `pass`: Placeholder for empty code blocks.
- `del`: Delete objects.
  ```python
  del my_list[0]  # Remove first element
  ```

---

This list covers **core Python syntax** for variables, control flow, functions, data structures, OOP, and advanced features. For full documentation, refer to the [Python Official Docs](https://docs.python.org/3/).
