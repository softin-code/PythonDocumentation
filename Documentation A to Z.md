Here’s a comprehensive list of **Python syntax** with examples and descriptions, organized by category:

---

### **1. Variables and Data Types**
#### **1.1. Variable Assignment**
Python uses dynamic typing (no explicit type declaration). Variables are created when assigned.  
**Syntax**:
```python
variable_name = value
```

**Examples**:
```python
age = 25                   # Integer
price = 19.99              # Float
name = "Alice"             # String
is_active = True           # Boolean (True/False)
result = None              # NoneType (represents absence of value)
```

---

#### **1.2. Core Data Types**
##### **a. Numeric Types**
- **Integer (`int`)**:
  ```python
  x = 42                   # Whole numbers (positive, negative, or zero)
  y = -10
  ```
- **Float (`float`)**:
  ```python
  pi = 3.1415              # Decimal numbers
  temperature = -5.6
  ```
- **Complex (`complex`)**:
  ```python
  z = 3 + 4j               # Complex numbers (real + imaginary part)
  ```

##### **b. Text Type**
- **String (`str`)**:
  ```python
  greeting = "Hello"       # Enclosed in single/double/triple quotes
  address = '''123 Main St,
  New York'''              # Multi-line string
  ```

##### **c. Boolean (`bool`)**
```python
is_valid = True            # Only two values: True or False
is_empty = False
```

##### **d. NoneType (`None`)**
```python
empty_value = None         # Represents "no value" or "null"
```

---

#### **1.3. Collections**
##### **a. List (`list`)**
```python
fruits = ["apple", "banana", "cherry"]  # Ordered, mutable, allows duplicates
numbers = [1, 2.5, 3+4j]               # Mixed data types
```

##### **b. Tuple (`tuple`)**
```python
coordinates = (10, 20)     # Ordered, immutable, allows duplicates
rgb = (255, 0, 0)
```

##### **c. Set (`set`)**
```python
unique_ids = {101, 102, 103}  # Unordered, mutable, no duplicates
empty_set = set()             # Use set() instead of {} (which creates a dict)
```

##### **d. Dictionary (`dict`)**
```python
user = {"name": "Bob", "age": 30}  # Key-value pairs (keys must be immutable)
scores = {"math": 90, "science": 85}
```

---

#### **1.4. Type Checking**
Use the `type()` function to check the data type:
```python
print(type(age))        # <class 'int'>
print(type(name))       # <class 'str'>
print(type(is_active))  # <class 'bool'>
```

---

#### **1.5. Type Conversion**
Convert between types using built-in functions:
```python
num_str = "123"
num_int = int(num_str)   # Convert string to integer: 123

float_to_int = int(3.9)  # Truncates to 3 (decimal part removed)

int_to_str = str(42)     # "42"

bool_to_int = int(True)  # 1 (False → 0)
```

---

#### **1.6. Variable Naming Rules**
- Start with a letter or `_`
- Followed by letters, numbers, or `_`
- Case-sensitive (`Age ≠ age`)
- Avoid reserved keywords (`if`, `for`, etc.)

**Valid**:
```python
_count = 5
user2 = "John"
total_price = 99.99
```

**Invalid**:
```python
2user = "Alice"   # Starts with a number
class = "CS101"   # Reserved keyword
```

---

#### **1.7. Dynamic Typing**
Variables can be reassigned to different types:
```python
value = 10        # Initially an integer
value = "text"    # Now a string
value = [1, 2, 3] # Now a list
```

---

#### **1.8. Special Cases**
##### **Type Hints (Optional)**
```python
count: int = 0            # Variable type hint
def greet(name: str) -> str:  # Function argument/return type hints
    return f"Hello, {name}"
```

##### **Bytes and Bytearray**
```python
data = b"binary_data"     # Immutable bytes
mutable_data = bytearray(b"abc")  # Mutable bytearray
```

---

#### **Key Notes**
- **Immutability**: `int`, `float`, `str`, `bool`, `tuple`, and `bytes` cannot be modified after creation.
- **Mutability**: `list`, `dict`, `set`, and `bytearray` can be modified in-place.
- **Integer Size**: Python integers have unlimited precision (no overflow).

---

### **2. Basic Operators**

#### **2.1 Arithmetic Operators**  
Used for mathematical operations.  
```python
print(5 + 3)    # 8 (Addition)  
print(10 - 2)   # 8 (Subtraction)  
print(4 * 3)    # 12 (Multiplication)  
print(10 / 3)   # 3.333... (Division)  
print(10 // 3)  # 3 (Floor Division)  
print(10 % 3)   # 1 (Modulus/Remainder)  
print(2 ** 3)   # 8 (Exponentiation)  
```

---

#### **2.2 Assignment Operators**  
Assign values to variables and update them.  
```python
x = 5           # Assign  
x += 3          # x = x + 3 → 8  
x -= 2          # x = x - 2 → 6  
x *= 4          # x = x * 4 → 24  
x /= 3          # x = x / 3 → 8.0  
x **= 2         # x = x ** 2 → 64.0  
x %= 10         # x = x % 10 → 4.0  
```

---

#### **2.3 Comparison Operators**  
Return `True` or `False` based on comparisons.  
```python
a = 10  
b = 20  
print(a == b)   # False (Equal to)  
print(a != b)   # True (Not equal to)  
print(a > b)    # False (Greater than)  
print(a <= b)   # True (Less than or equal to)  
print("apple" == "apple")  # True (String comparison)  
```

---

#### **2.4 Logical Operators**  
Combine conditional statements.  
```python
x = True  
y = False  
print(x and y)  # False (Both must be True)  
print(x or y)   # True (At least one True)  
print(not x)    # False (Inverts the boolean)  
```

---

#### **2.5 Bitwise Operators**  
Perform operations on binary representations.  
```python
a = 5  # Binary: 0101  
b = 3  # Binary: 0011  
print(a & b)   # 1 (AND: 0001)  
print(a | b)   # 7 (OR: 0111)  
print(a ^ b)   # 6 (XOR: 0110)  
print(~a)      # -6 (NOT: Inverts bits)  
print(a << 1)  # 10 (Left shift: 0101 → 1010)  
print(a >> 1)  # 2 (Right shift: 0101 → 0010)  
```

---

#### **2.6 Identity Operators**  
Check if two objects are the same in memory.  
```python
x = [1, 2]  
y = [1, 2]  
z = x  
print(x is z)     # True (Same object)  
print(x is y)     # False (Different objects, even if values match)  
print(x == y)     # True (Values are equal)  
print(x is not y) # True  
```

---

#### **2.7 Membership Operators**  
Check if a value exists in a sequence.  
```python
fruits = ["apple", "banana"]  
print("apple" in fruits)       # True  
print("mango" not in fruits)   # True  
print("a" in "apple")          # True (Works with strings)  
```

---

#### **2.8 Operator Precedence**  
Order of evaluation (highest to lowest):  
1. **Parentheses `()`**  
2. **Exponentiation `**`**  
3. **Bitwise NOT `~`, Unary `+`, `-`**  
4. **Multiplication `*`, Division `/`, Floor `//`, Modulus `%`**  
5. **Addition `+`, Subtraction `-`**  
6. **Bitwise Shifts `<<`, `>>`**  
7. **Bitwise AND `&`**  
8. **Bitwise XOR `^`, OR `|`**  
9. **Comparison `==`, `!=`, `>`, `<`, `>=`, `<=`**  
10. **Logical NOT `not`**  
11. **Logical AND `and`**  
12. **Logical OR `or`**  

**Example**:  
```python
result = 5 + 3 * 2 ** 2  # 5 + (3 * (2^2)) → 5 + 12 = 17  
print(result)  
```

---

### **3. Control Flow**

#### **3.1 Conditional Statements (`if`, `elif`, `else`)**  
Execute code blocks based on conditions.  
```python  
x = 10  
if x > 0:  
    print("Positive")  
elif x == 0:  
    print("Zero")  
else:  
    print("Negative")  
```  
- **Indentation**: Code blocks are defined using indentation (4 spaces or a tab).  
- **Order**: `if` → `elif` (optional, multiple allowed) → `else` (optional).  

---

#### **3.2 `for` Loops**  
Iterate over sequences (lists, tuples, strings, etc.).  
```python  
fruits = ["apple", "banana", "cherry"]  
for fruit in fruits:  
    print(fruit)  # Prints each fruit  

# Using range()  
for i in range(3):  # 0, 1, 2  
    print(i)  
```  
- **`range(start, stop, step)`**: Generates a sequence of numbers.  

---

#### **3.3 `while` Loops**  
Repeat code while a condition is `True`.  
```python  
count = 0  
while count < 3:  
    print(count)  # 0, 1, 2  
    count += 1  # Ensure the loop terminates!  
```  
- **Avoid infinite loops**: Ensure the condition eventually becomes `False`.  

---

#### **3.4 `break` Statement**  
Exit a loop immediately.  
```python  
for num in [1, 2, 3, 4, 5]:  
    if num == 3:  
        break  # Loop stops here  
    print(num)  # 1, 2  
```  

---

#### **3.5 `continue` Statement**  
Skip the rest of the current iteration and move to the next.  
```python  
for num in [1, 2, 3, 4]:  
    if num % 2 == 0:  
        continue  # Skip even numbers  
    print(num)  # 1, 3  
```  

---

#### **3.6 `else` Clause in Loops**  
Executes if the loop completes normally (not terminated by `break`).  
```python  
for num in [1, 2, 3]:  
    print(num)  
else:  
    print("Loop finished!")  # Always runs if no break  

# With break  
for num in [1, 2, 3]:  
    if num == 2:  
        break  
else:  
    print("This won’t execute")  
```  

---

#### **3.7 `pass` Statement**  
A placeholder for empty code blocks.  
```python  
if x > 10:  
    pass  # Do nothing (avoids syntax errors)  
else:  
    print("x is small")  
```  

---

### **Key Notes**  
- **Nested Control Flow**:  
  ```python  
  for i in range(2):  
      if i == 0:  
          print("First iteration")  
      else:  
          print("Second iteration")  
  ```  
- **Ternary Operator**: Shorthand for simple conditionals.  
  ```python  
  result = "Even" if x % 2 == 0 else "Odd"  
  ```  

---

### **4. Functions**

#### **4.1 Function Definition (`def`)**  
Define a function using `def`.  
```python  
def greet(name):  
    """Print a greeting."""  # Docstring (optional documentation)  
    print(f"Hello, {name}!")  

greet("Alice")  # Output: Hello, Alice!  
```  

---

#### **4.2 Return Statement**  
Use `return` to send a value back from a function.  
```python  
def add(a, b):  
    return a + b  

result = add(3, 5)  # result = 8  
```  

---

#### **4.3 Parameters and Arguments**  
- **Positional Arguments**: Matched by order.  
  ```python  
  def power(base, exponent):  
      return base ** exponent  

  print(power(2, 3))  # 8 (2^3)  
  ```  

- **Keyword Arguments**: Matched by parameter name.  
  ```python  
  print(power(exponent=3, base=2))  # 8  
  ```  

- **Default Parameters**: Assign default values.  
  ```python  
  def greet(name="Guest"):  
      print(f"Hello, {name}!")  

  greet()  # Hello, Guest!  
  ```  

---

#### **4.4 Variable-Length Arguments**  
- **`*args`**: Accepts positional arguments as a tuple.  
  ```python  
  def sum_all(*args):  
      return sum(args)  

  print(sum_all(1, 2, 3))  # 6  
  ```  

- **`**kwargs`**: Accepts keyword arguments as a dictionary.  
  ```python  
  def print_details(**kwargs):  
      for key, value in kwargs.items():  
          print(f"{key}: {value}")  

  print_details(name="Alice", age=30)  
  ```  

---

#### **4.5 Lambda Functions**  
Anonymous functions defined with `lambda`.  
```python  
square = lambda x: x ** 2  
print(square(4))  # 16  

# Use-case: Sorting with a key  
points = [(1, 2), (3, 1), (5, 0)]  
points.sort(key=lambda point: point[1])  # Sort by y-coordinate  
```  

---

#### **4.6 Scope and `global`/`nonlocal`**  
- **Local vs Global Scope**:  
  ```python  
  x = 10  # Global variable  

  def update():  
      global x  
      x = 20  # Modify global x  

  update()  
  print(x)  # 20  
  ```  

- **`nonlocal`**: Modify variables in nested functions.  
  ```python  
  def outer():  
      count = 0  
      def inner():  
          nonlocal count  
          count += 1  
      inner()  
      print(count)  # 1  
  ```  

---

#### **4.7 Recursion**  
Functions that call themselves.  
```python  
def factorial(n):  
    if n == 1:  
        return 1  
    else:  
        return n * factorial(n-1)  

print(factorial(5))  # 120  
```  

---

#### **4.8 Decorators**  
Modify or enhance functions without changing their code.  
```python  
def logger(func):  
    def wrapper(*args):  
        print(f"Calling {func.__name__}")  
        return func(*args)  
    return wrapper  

@logger  
def add(a, b):  
    return a + b  

add(2, 3)  # Output: "Calling add" → returns 5  
```  

---

#### **4.9 Type Hints**  
Specify expected data types (optional but recommended).  
```python  
def multiply(a: int, b: int) -> int:  
    return a * b  
```  

---

#### **4.10 Docstrings**  
Document functions using triple-quoted strings.  
```python  
def greet(name):  
    """Return a greeting message.  
      
    Args:  
        name (str): The name to greet.  
      
    Returns:  
        str: The greeting.  
    """  
    return f"Hello, {name}!"  

print(greet.__doc__)  # View the docstring  
```  

---

### **Key Notes**  
- **Immutability**: Parameters passed by assignment (immutable types like `int` are copied, mutable types like `list` are referenced).  
- **First-Class Objects**: Functions can be assigned to variables, passed as arguments, or returned from other functions.  

---

### **5. Data Structures**

#### **5.1 Lists (`list`)**  
Ordered, mutable, allows duplicates.  
```python  
fruits = ["apple", "banana", "cherry"]  
numbers = [1, 2, 3]  

# Key Operations  
fruits.append("orange")      # Add to end  
fruits.insert(1, "mango")    # Insert at index  
fruits.remove("banana")      # Remove by value  
popped = fruits.pop(0)       # Remove by index (returns "apple")  
sliced = numbers[1:3]        # [2, 3] (slicing)  
numbers.sort()               # In-place sort  
```

---

#### **5.2 Tuples (`tuple`)**  
Ordered, **immutable**, allows duplicates.  
```python  
point = (3, 4)  
colors = ("red", "green", "blue")  

# Key Features  
x, y = point                 # Unpacking  
combined = point + (5,)      # New tuple (3, 4, 5)  
index = colors.index("red")  # 0  
count = colors.count("red")  # 1  
```

---

#### **5.3 Dictionaries (`dict`)**  
Unordered, mutable, key-value pairs (keys must be hashable).  
```python  
person = {"name": "Alice", "age": 30}  

# Key Operations  
person["email"] = "alice@example.com"  # Add/update key  
age = person.get("age", 0)             # 30 (default 0 if missing)  
keys = person.keys()                   # ["name", "age", "email"]  
del person["age"]                      # Remove key  
```

---

#### **5.4 Sets (`set`)**  
Unordered, mutable, unique elements.  
```python  
primes = {2, 3, 5, 7}  
evens = set([2, 4, 6, 8])  

# Key Operations  
primes.add(11)                # {2, 3, 5, 7, 11}  
primes.remove(2)              # Remove element  
union = primes | evens        # {2, 3, 5, 7, 11, 4, 6, 8}  
intersection = primes & evens # {2}  
```

---

#### **5.5 Strings (`str`)**  
Immutable sequence of Unicode characters.  
```python  
text = "Hello, World!"  

# Key Operations  
substring = text[0:5]         # "Hello"  
upper = text.upper()          # "HELLO, WORLD!"  
split = text.split(",")       # ["Hello", " World!"]  
replaced = text.replace("H", "J")  # "Jello, World!"  
```

---

#### **5.6 Advanced Structures**  
- **`collections.deque`**: Efficient double-ended queue.  
  ```python  
  from collections import deque  
  queue = deque(["a", "b"])  
  queue.appendleft("x")  # ["x", "a", "b"]  
  queue.pop()            # "b"  
  ```  

- **`collections.defaultdict`**: Dictionary with default values.  
  ```python  
  from collections import defaultdict  
  counter = defaultdict(int)  
  counter["a"] += 1  # {"a": 1}  
  ```  

- **`frozenset`**: Immutable version of `set`.  
  ```python  
  immutable_set = frozenset([1, 2, 3])  
  ```

---

#### **5.7 Comprehensions**  
Create lists/dictionaries/sets concisely.  
```python  
# List Comprehension  
squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]  

# Dict Comprehension  
square_dict = {x: x**2 for x in range(3)}  # {0: 0, 1: 1, 2: 4}  

# Set Comprehension  
unique_chars = {char for char in "apple"}  # {'a', 'p', 'l', 'e'}  
```

---

### **Key Notes**  
- **Mutability**:  
  - Mutable: `list`, `dict`, `set`  
  - Immutable: `tuple`, `str`, `frozenset`, `int`, `float`  
- **Ordering**:  
  - Ordered: `list`, `tuple`, `str`, `dict` (Python 3.7+ preserves insertion order)  
  - Unordered: `set`  

---

### **6. String Operations**

#### **6.1 String Creation and Basics**  
Strings are immutable sequences of Unicode characters.  
```python  
s1 = 'Hello'              # Single quotes  
s2 = "World"              # Double quotes  
s3 = '''Multiline  
string'''                 # Triple quotes for multiline  
s4 = "He said, \"Hi!\""   # Escape characters (\", \', \n, \t, etc.)  
raw_str = r"C:\path\name" # Raw string (ignores escape characters)  
```

---

#### **6.2 Common String Methods**  
**Case Manipulation**:  
```python  
text = "Python"  
print(text.upper())       # "PYTHON"  
print(text.lower())       # "python"  
print("hello".capitalize())  # "Hello"  
```  

**Whitespace Handling**:  
```python  
msg = "   Hello   "  
print(msg.strip())        # "Hello" (removes leading/trailing spaces)  
```  

**Splitting and Joining**:  
```python  
csv = "apple,banana,cherry"  
fruits = csv.split(",")   # ["apple", "banana", "cherry"]  
joined = "-".join(fruits) # "apple-banana-cherry"  
```  

**Search and Replace**:  
```python  
s = "Hello World"  
print(s.find("World"))    # 6 (index of substring)  
print(s.replace("World", "Python"))  # "Hello Python"  
```  

---

#### **6.3 String Formatting**  
**f-Strings (Python 3.6+)**:  
```python  
name = "Alice"  
age = 30  
print(f"{name} is {age} years old.")  # "Alice is 30 years old."  
```  

**`format()` Method**:  
```python  
print("{} + {} = {}".format(2, 3, 5))  # "2 + 3 = 5"  
```  

**Old-Style (`%` Operator)**:  
```python  
print("Price: $%.2f" % 99.99)  # "Price: $99.99"  
```  

---

#### **6.4 String Slicing and Indexing**  
```python  
text = "Python"  
print(text[0])          # "P"  
print(text[-1])         # "n" (last character)  
print(text[1:4])        # "yth" (indices 1-3)  
print(text[::-1])       # "nohtyP" (reverse string)  
```  

---

#### **6.5 String Concatenation and Repetition**  
```python  
s1 = "Hello"  
s2 = "World"  
print(s1 + " " + s2)    # "Hello World"  
print("Hi" * 3)         # "HiHiHi"  
```  

---

#### **6.6 Checking Substrings**  
```python  
s = "Hello World"  
print("World" in s)     # True  
print("Python" not in s) # True  
```  

---

#### **6.7 String Encoding/Decoding**  
Convert between strings and bytes:  
```python  
text = "Python"  
encoded = text.encode("utf-8")  # b'Python' (bytes object)  
decoded = encoded.decode("utf-8")  # "Python"  
```  

---

#### **6.8 Advanced String Operations**  
**String Validation**:  
```python  
print("123".isdigit())  # True  
print("abc123".isalnum()) # True  
print("   ".isspace())  # True  
```  

**Partitioning**:  
```python  
s = "apple:banana:cherry"  
print(s.partition(":"))  # ('apple', ':', 'banana:cherry')  
```  

**Padding and Alignment**:  
```python  
print("Python".ljust(10, "-"))  # "Python----"  
print("42".zfill(5))            # "00042"  
```  

---

### **Key Notes**  
- **Immutability**: Strings cannot be modified in-place (e.g., `s[0] = "X"` is invalid).  
- **Ordering**: Strings are ordered sequences (indexable and iterable).  
- **Useful Modules**: For advanced text processing, use `re` (regex) or `string` modules.  

---

### **7. Error Handling**

#### **7.1 Basic `try`/`except` Block**  
Catch and handle exceptions to prevent program crashes.  
```python  
try:  
    result = 10 / 0  
except ZeroDivisionError:  
    print("Cannot divide by zero!")  
```  
- Catches `ZeroDivisionError` and prints a message instead of crashing.  

---

#### **7.2 Handling Multiple Exceptions**  
Catch different exceptions with separate blocks.  
```python  
try:  
    num = int("text")  # Raises ValueError  
    print(10 / 0)  
except ValueError:  
    print("Invalid number!")  
except ZeroDivisionError:  
    print("Division by zero!")  
```  
- Use multiple `except` clauses for different error types.  

**Catching Multiple Exceptions in One Block**:  
```python  
try:  
    # Risky code  
except (TypeError, KeyError):  
    print("Type or Key error occurred!")  
```  

---

#### **7.3 `else` Clause**  
Executes if no exceptions are raised in the `try` block.  
```python  
try:  
    result = 10 / 2  
except ZeroDivisionError:  
    print("Division failed!")  
else:  
    print(f"Result: {result}")  # Runs if no error  
```  

---

#### **7.4 `finally` Clause**  
Runs **always**, whether an exception occurred or not.  
```python  
try:  
    file = open("data.txt", "r")  
    content = file.read()  
except FileNotFoundError:  
    print("File not found!")  
finally:  
    file.close()  # Ensure file is closed  
```  

---

#### **7.5 Raising Exceptions (`raise`)**  
Manually trigger exceptions using `raise`.  
```python  
def validate_age(age):  
    if age < 0:  
        raise ValueError("Age cannot be negative!")  

try:  
    validate_age(-5)  
except ValueError as e:  
    print(e)  # "Age cannot be negative!"  
```  

**Re-raising Exceptions**:  
```python  
try:  
    # Code that might fail  
except ValueError:  
    print("Handled locally, then re-raise")  
    raise  # Propagates the exception upward  
```  

---

#### **7.6 Custom Exceptions**  
Create user-defined exceptions by subclassing `Exception`.  
```python  
class InvalidEmailError(Exception):  
    """Raised for invalid email formats."""  

def validate_email(email):  
    if "@" not in email:  
        raise InvalidEmailError(f"Invalid email: {email}")  

try:  
    validate_email("user.example.com")  
except InvalidEmailError as e:  
    print(e)  
```  

---

#### **7.7 `assert` Statement**  
Check conditions (used for debugging). Raises `AssertionError` if false.  
```python  
def calculate_area(radius):  
    assert radius > 0, "Radius must be positive!"  
    return 3.14 * radius ** 2  

calculate_area(-2)  # Triggers AssertionError  
```  

---

#### **7.8 Built-in Exceptions**  
Common exception types:  
- `ValueError`: Invalid value (e.g., `int("text")`).  
- `TypeError`: Incorrect type (e.g., `"5" + 3`).  
- `KeyError`: Missing dictionary key.  
- `IndexError`: List index out of range.  
- `FileNotFoundError`: Missing file.  

---

#### **7.9 Exception Propagation**  
Exceptions bubble up through the call stack until caught.  
```python  
def func1():  
    func2()  

def func2():  
    raise ValueError("Error from func2")  

try:  
    func1()  
except ValueError as e:  
    print(f"Caught: {e}")  # Catches the propagated error  
```  

---

### **Key Notes**  
- **Base Class**: All exceptions inherit from `BaseException` (use `Exception` for user-defined errors).  
- **Cleanup**: Use `finally` or context managers (`with`) for resource cleanup (e.g., closing files).  
- **Avoid Silent Failures**: Always log or handle exceptions meaningfully.  

---

### **8. Object-Oriented Programming (OOP)**

#### **8.1 Class Definition and Objects**  
Define a class with the `class` keyword. Create objects (instances) by calling the class.  
```python  
class Dog:  
    # Class-level attribute (shared by all instances)  
    species = "Canis familiaris"  

    # Constructor (__init__ method)  
    def __init__(self, name, age):  
        self.name = name  # Instance attribute  
        self.age = age  

# Create an instance  
dog1 = Dog("Buddy", 3)  
print(dog1.name)  # "Buddy"  
```

---

#### **8.2 Inheritance**  
Create subclasses to inherit attributes and methods from a parent class.  
```python  
class GoldenRetriever(Dog):  # Inherits from Dog  
    def speak(self, sound="Woof"):  
        return f"{self.name} says {sound}!"  

dog2 = GoldenRetriever("Max", 2)  
print(dog2.speak())  # "Max says Woof!"  
```

---

#### **8.3 Encapsulation (Private/Protected Members)**  
Use naming conventions to control access:  
- **Protected**: `_variable` (accessible but treated as non-public).  
- **Private**: `__variable` (name mangling makes it harder to access).  

```python  
class Account:  
    def __init__(self, balance):  
        self.__balance = balance  # Private attribute  

    def deposit(self, amount):  
        self.__balance += amount  

account = Account(100)  
# account.__balance  # Error (use name mangling: _Account__balance)  
```

---

#### **8.4 Polymorphism and Method Overriding**  
Subclasses can override parent methods.  
```python  
class Cat:  
    def speak(self):  
        return "Meow!"  

class Lion(Cat):  
    def speak(self):  # Override parent method  
        return "Roar!"  

animals = [Cat(), Lion()]  
for animal in animals:  
    print(animal.speak())  # "Meow!", "Roar!"  
```

---

#### **8.5 Abstract Base Classes (ABCs)**  
Enforce method implementation in subclasses.  
```python  
from abc import ABC, abstractmethod  

class Shape(ABC):  
    @abstractmethod  
    def area(self):  
        pass  

class Circle(Shape):  
    def __init__(self, radius):  
        self.radius = radius  

    def area(self):  # Must be implemented  
        return 3.14 * self.radius ** 2  
```

---

#### **8.6 Class and Static Methods**  
- **Class Method**: Acts on the class (uses `@classmethod`).  
- **Static Method**: Utility function (uses `@staticmethod`).  

```python  
class MyClass:  
    @classmethod  
    def from_string(cls, data):  
        return cls(data)  

    @staticmethod  
    def is_positive(num):  
        return num > 0  
```

---

#### **8.7 Special Methods (Magic Methods)**  
Customize object behavior with double-underscore methods.  
```python  
class Vector:  
    def __init__(self, x, y):  
        self.x = x  
        self.y = y  

    def __add__(self, other):  # Overload + operator  
        return Vector(self.x + other.x, self.y + other.y)  

    def __repr__(self):  # String representation  
        return f"Vector({self.x}, {self.y})"  

v1 = Vector(2, 3)  
v2 = Vector(1, 4)  
print(v1 + v2)  # Vector(3, 7)  
```

---

#### **8.8 Properties (Getters/Setters)**  
Use `@property` to control attribute access.  
```python  
class Temperature:  
    def __init__(self, celsius):  
        self._celsius = celsius  

    @property  
    def celsius(self):  
        return self._celsius  

    @celsius.setter  
    def celsius(self, value):  
        if value < -273.15:  
            raise ValueError("Too cold!")  
        self._celsius = value  

temp = Temperature(25)  
temp.celsius = 30  # Uses the setter  
```

---

#### **8.9 Composition vs. Inheritance**  
**Composition**: Build classes using other classes (has-a relationship).  
```python  
class Engine:  
    def start(self):  
        print("Engine started")  

class Car:  
    def __init__(self):  
        self.engine = Engine()  

my_car = Car()  
my_car.engine.start()  
```

---

#### **8.10 Multiple Inheritance and MRO**  
Python supports inheriting from multiple classes.  
```python  
class A:  
    def greet(self):  
        print("A says hello")  

class B(A):  
    def greet(self):  
        print("B says hello")  

class C(A):  
    def greet(self):  
        print("C says hello")  

class D(B, C):  
    pass  

d = D()  
d.greet()  # "B says hello" (Method Resolution Order: D → B → C → A)  
```

---

#### **8.11 Operator Overloading**  
Define custom behavior for operators (e.g., `+`, `==`).  
```python  
class Book:  
    def __init__(self, title, pages):  
        self.title = title  
        self.pages = pages  

    def __eq__(self, other):  
        return self.title == other.title  

book1 = Book("Python 101", 300)  
book2 = Book("Python 101", 250)  
print(book1 == book2)  # True (compares titles)  
```

---

#### **8.12 Class Decorators**  
Modify class behavior dynamically.  
```python  
def add_method(cls):  
    def greet(self):  
        return "Hello from decorator!"  
    cls.greet = greet  
    return cls  

@add_method  
class MyClass:  
    pass  

obj = MyClass()  
print(obj.greet())  # "Hello from decorator!"  
```

---

#### **8.13 Using `super()`**  
Call parent class methods in inheritance hierarchies.  
```python  
class Parent:  
    def __init__(self, name):  
        self.name = name  

class Child(Parent):  
    def __init__(self, name, age):  
        super().__init__(name)  # Call Parent's __init__  
        self.age = age  
```

---

#### **8.14 `__slots__` for Memory Efficiency**  
Restrict class attributes to save memory.  
```python  
class Point:  
    __slots__ = ["x", "y"]  # Only x and y are allowed  
    def __init__(self, x, y):  
        self.x = x  
        self.y = y  

p = Point(3, 4)  
# p.z = 5  # AttributeError (not in __slots__)  
```

---

### **Key Notes**  
- **`self`**: Refers to the instance (explicitly passed in method calls).  
- **Class vs. Instance Attributes**:  
  - Class attributes are shared across all instances.  
  - Instance attributes are unique to each object.  
- **Method Resolution Order (MRO)**: Determines the search order for methods in inheritance hierarchies.  

---

### **9. File Handling Syntax and Operations**
#### **9.1. Opening Files**
Use the `open()` function with a file path and mode. Always use a `with` statement for automatic resource cleanup.

```python
# Syntax
with open("filename.txt", "mode") as file:
    # Perform operations
```

**Common Modes**:
- `"r"`: Read (default mode)
- `"w"`: Write (overwrites existing file)
- `"a"`: Append (adds to existing file)
- `"r+"`: Read and write
- `"b"`: Binary mode (e.g., `"rb"` for reading binary files)

---

#### **9.2. Reading Files**
**Read Entire Content**:
```python
with open("data.txt", "r") as file:
    content = file.read()  # Returns entire content as a string
```

**Read Line by Line**:
```python
with open("data.txt", "r") as file:
    for line in file:  # Iterate over lines
        print(line.strip())  # .strip() removes newline characters
```

**Read All Lines into a List**:
```python
with open("data.txt", "r") as file:
    lines = file.readlines()  # Returns list of lines
```

---

#### **9.3. Writing Files**
**Write New Content** (Overwrites existing file):
```python
with open("output.txt", "w") as file:
    file.write("Hello, World!\n")  # \n for newline
    file.writelines(["Line 1\n", "Line 2\n"])  # Write multiple lines
```

**Append to Existing File**:
```python
with open("log.txt", "a") as file:
    file.write("New log entry\n")
```

---

#### **9.4. Working with Binary Files**
```python
# Copy an image (read binary, write binary)
with open("input.jpg", "rb") as src:
    with open("copy.jpg", "wb") as dest:
        dest.write(src.read())
```

---

#### **9.5. File Pointer Control**
- `seek(offset)`: Move the file pointer to a specific position.
- `tell()`: Get the current pointer position.

```python
with open("data.txt", "r") as file:
    print(file.tell())   # 0 (start of file)
    file.seek(10)        # Move to 10th byte
    print(file.tell())   # 10
```

---

#### **9.6. Error Handling**
Handle missing files or permissions:
```python
try:
    with open("missing_file.txt", "r") as file:
        print(file.read())
except FileNotFoundError:
    print("File not found!")
except IOError:
    print("An I/O error occurred.")
```

---

### **Key Notes**
1. **Always Close Files**: The `with` statement automatically closes files.
2. **File Paths**: Use absolute paths (e.g., `/home/user/file.txt`) or relative paths (e.g., `data/file.txt`).
3. **Check File Existence**:
   ```python
   import os
   if os.path.exists("data.txt"):
       print("File exists!")
   ```

---

### **Common Use Cases**
1. **Read Configuration File**:
   ```python
   config = {}
   with open("config.cfg", "r") as file:
       for line in file:
           key, value = line.strip().split("=")
           config[key] = value
   ```

2. **Write CSV Data**:
   ```python
   data = ["Alice,30", "Bob,25"]
   with open("users.csv", "w") as file:
       file.write("Name,Age\n")
       file.writelines(data)
   ```

---

### **10. Advanced Features**

#### **10.1 List Comprehensions and Generator Expressions**  
**List Comprehension**:  
```python  
squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]  
```  

**Generator Expression**:  
```python  
gen = (x**2 for x in range(5))  # Lazy evaluation  
print(list(gen))  # [0, 1, 4, 9, 16]  
```  

---

#### **10.2 Walrus Operator (`:=`)**  
Assign variables within expressions (Python 3.8+).  
```python  
while (line := input("Enter text: ")) != "quit":  
    print(f"You entered: {line}")  
```  

---

#### **10.3 Decorators**  
Modify or enhance functions dynamically.  
```python  
def logger(func):  
    def wrapper(*args):  
        print(f"Calling {func.__name__}")  
        return func(*args)  
    return wrapper  

@logger  
def add(a, b):  
    return a + b  

add(2, 3)  # Output: "Calling add" → returns 5  
```  

---

#### **10.4 Context Managers (`with`)**  
Manage resources (e.g., files) cleanly.  
```python  
with open("file.txt", "r") as file:  
    content = file.read()  # File automatically closed  
```  

**Custom Context Manager**:  
```python  
from contextlib import contextmanager  

@contextmanager  
def timer():  
    import time  
    start = time.time()  
    yield  
    print(f"Time: {time.time() - start} sec")  

with timer():  
    time.sleep(2)  # Prints "Time: 2.0 sec"  
```  

---

#### **10.5 Asynchronous Programming (`async`/`await`)**  
Write concurrent code with coroutines.  
```python  
import asyncio  

async def fetch_data():  
    print("Fetching data...")  
    await asyncio.sleep(1)  
    return "Data"  

async def main():  
    result = await fetch_data()  
    print(result)  

asyncio.run(main())  # Output: "Fetching data..." → "Data"  
```  

---

#### **10.6 Metaclasses**  
Define custom class creation logic.  
```python  
class Meta(type):  
    def __new__(cls, name, bases, dct):  
        dct["version"] = 1.0  
        return super().__new__(cls, name, bases, dct)  

class MyClass(metaclass=Meta):  
    pass  

print(MyClass.version)  # 1.0  
```  

---

#### **10.7 Operator Overloading**  
Customize behavior for operators (e.g., `+`, `==`).  
```python  
class Vector:  
    def __init__(self, x, y):  
        self.x = x  
        self.y = y  

    def __add__(self, other):  
        return Vector(self.x + other.x, self.y + other.y)  

v1 = Vector(2, 3)  
v2 = Vector(1, 4)  
v3 = v1 + v2  # Vector(3, 7)  
```  

---

#### **10.8 Descriptors**  
Control attribute access with `__get__`, `__set__`, and `__delete__`.  
```python  
class PositiveNumber:  
    def __set__(self, instance, value):  
        if value < 0:  
            raise ValueError("Must be positive!")  
        instance.__dict__[self.name] = value  

    def __set_name__(self, owner, name):  
        self.name = name  

class Order:  
    price = PositiveNumber()  

order = Order()  
order.price = 50  # Works  
# order.price = -10  # Raises ValueError  
```  

---

#### **10.9 Type Hints and `typing` Module**  
Add static type annotations.  
```python  
from typing import List, Dict, Optional  

def greet(name: str) -> str:  
    return f"Hello, {name}"  

def process(data: List[Dict[str, int]]) -> Optional[float]:  
    ...  
```  

---

#### **10.10 Pattern Matching (Python 3.10+)**  
Use `match`/`case` for structural pattern matching.  
```python  
def check_value(value):  
    match value:  
        case 0:  
            print("Zero")  
        case [x, y]:  
            print(f"List with two elements: {x}, {y}")  
        case {"key": val}:  
            print(f"Dict with 'key': {val}")  
        case _:  
            print("Unknown")  

check_value([1, 2])  # "List with two elements: 1, 2"  
```  

---

#### **10.11 `functools` Utilities**  
**`lru_cache`**: Memoize function results.  
```python  
from functools import lru_cache  

@lru_cache(maxsize=128)  
def fibonacci(n):  
    if n < 2:  
        return n  
    return fibonacci(n-1) + fibonacci(n-2)  
```  

**`partial`**: Pre-fill function arguments.  
```python  
from functools import partial  

pow_2 = partial(pow, exp=2)  
print(pow_2(5))  # 25  
```  

---

#### **10.12 `itertools` Tools**  
**Infinite Iterators**:  
```python  
from itertools import count, cycle  

for i in count(start=0, step=2):  # 0, 2, 4, ...  
    if i > 10:  
        break  
    print(i)  
```  

**Combinations**:  
```python  
from itertools import combinations  

print(list(combinations("ABC", 2)))  # [('A', 'B'), ('A', 'C'), ('B', 'C')]  
```  

---

#### **10.13 `__slots__` for Memory Optimization**  
Restrict class attributes to save memory.  
```python  
class Point:  
    __slots__ = ["x", "y"]  
    def __init__(self, x, y):  
        self.x = x  
        self.y = y  

p = Point(3, 4)  
# p.z = 5  # AttributeError (not in __slots__)  
```  

---

#### **10.14 Dynamic Attribute Access**  
Use `__getattr__`, `__setattr__`, and `__getattribute__`.  
```python  
class DynamicAttributes:  
    def __getattr__(self, name):  
        return f"Attribute {name} not found!"  

obj = DynamicAttributes()  
print(obj.color)  # "Attribute color not found!"  
```  

---

### **Key Notes**  
- **Performance**: Use generators for large datasets to save memory.  
- **Concurrency**: `asyncio` is ideal for I/O-bound tasks.  
- **Readability**: Use type hints and pattern matching for cleaner code.  

---

### **11. Walrus Operator (`:=`)**  
Introduced in Python 3.8, the walrus operator allows **assignment within expressions**, streamlining code by combining assignment and evaluation.

---

#### **11.1 Basic Syntax**  
Assign a value to a variable as part of an expression.  
```python  
# Without walrus  
n = len([1, 2, 3])  
if n > 2:  
    print(n)  

# With walrus  
if (n := len([1, 2, 3])) > 2:  
    print(n)  # 3  
```  
- The operator `:=` assigns `len([1, 2, 3])` to `n` and uses `n` in the condition.  

---

#### **11.2 Comparison to Traditional Assignment**  
Avoid redundant computations or repeated function calls.  
**Traditional Approach**:  
```python  
line = input("Enter text: ")  
while line != "quit":  
    print(f"You entered: {line}")  
    line = input("Enter text: ")  
```  

**With Walrus Operator**:  
```python  
while (line := input("Enter text: ")) != "quit":  
    print(f"You entered: {line}")  
```  

---

#### **11.3 Common Use Cases**  
**a. In Loops**  
Read and process input/files without redundant code.  
```python  
with open("data.txt", "r") as file:  
    while (chunk := file.read(1024)):  
        process(chunk)  
```  

**b. In Comprehensions**  
Avoid recomputing values in list/dict comprehensions.  
```python  
numbers = [1, 2, 3, 4]  
squares = [y for x in numbers if (y := x**2) > 4]  # [9, 16]  
```  

**c. In Conditionals**  
Check and use a value in one step.  
```python  
if (value := some_function()) is not None:  
    print(f"Result: {value}")  
```  

---

#### **11.4 Pitfalls and Limitations**  
- **Readability**: Overuse can make code harder to read.  
  ```python  
  # Bad practice (too nested)  
  result = (x := (y := 5) + 3) + y  
  ```  

- **Scope**: Variables assigned with `:=` are local to the current scope.  
- **Not Allowed in Augmented Assignments**:  
  ```python  
  (x := 5) += 1  # SyntaxError  
  ```  

---

#### **11.5 Performance Considerations**  
- **Efficiency**: Reduces redundant calculations.  
  ```python  
  # Without walrus  
  data = get_data()  
  if data:  
      process(data)  

  # With walrus (avoids calling get_data() twice)  
  if (data := get_data()):  
      process(data)  
  ```  

---

#### **11.6 Integration with Other Features**  
**a. With `f-strings`**:  
```python  
print(f"Result: {(x := 10)}")  # Result: 10  
```  

**b. In Lambda Functions**:  
```python  
func = lambda: (x := 5) * 2  
print(func())  # 10  
```  
- Note: Cannot assign to variables in lambda parameters directly.  

---

#### **11.7 Best Practices**  
- **Use Sparingly**: Prioritize readability over brevity.  
- **Parentheses**: Always wrap the walrus expression in parentheses.  
- **Avoid Deep Nesting**: Keep expressions simple.  

---

#### **11.8 Version Compatibility**  
- Requires **Python 3.8+**.  
- Code using `:=` will **not work** in older Python versions.  

---

### **Key Takeaways**  
- Simplifies code by combining assignment and evaluation.  
- Ideal for loops, comprehensions, and conditional checks.  
- Use cautiously to maintain readability.  

---

### **12. Asynchronous Programming**

#### **12.1 Coroutines and `async`/`await` Syntax**  
**Coroutines** are functions declared with `async def`. Use `await` to pause execution until an asynchronous operation completes.  
```python  
import asyncio  

async def fetch_data():  
    print("Fetching data...")  
    await asyncio.sleep(2)  # Non-blocking sleep  
    print("Data fetched!")  

# Run the coroutine  
asyncio.run(fetch_data())  
```  

---

#### **12.2 Event Loop**  
The event loop manages asynchronous tasks. Use `asyncio.run()` to execute coroutines (Python 3.7+).  
```python  
async def main():  
    await fetch_data()  

asyncio.run(main())  
```  

---

#### **12.3 Creating and Managing Tasks**  
**Tasks** run coroutines concurrently.  
```python  
async def task1():  
    await asyncio.sleep(1)  
    print("Task 1 done")  

async def task2():  
    await asyncio.sleep(2)  
    print("Task 2 done")  

async def main():  
    t1 = asyncio.create_task(task1())  
    t2 = asyncio.create_task(task2())  
    await t1  
    await t2  

asyncio.run(main())  # Both tasks run concurrently  
```  

---

#### **12.4 Futures**  
**Futures** represent eventual results. Tasks are a subclass of futures.  
```python  
async def set_future(fut):  
    await asyncio.sleep(1)  
    fut.set_result("Future done!")  

async def main():  
    loop = asyncio.get_running_loop()  
    fut = loop.create_future()  
    await set_future(fut)  
    print(fut.result())  # "Future done!"  

asyncio.run(main())  
```  

---

#### **12.5 Asynchronous Context Managers (`async with`)**  
Use `async with` to manage asynchronous resources (e.g., HTTP sessions).  
```python  
class AsyncContextManager:  
    async def __aenter__(self):  
        print("Entering context")  
        return self  

    async def __aexit__(self, *args):  
        print("Exiting context")  

async def main():  
    async with AsyncContextManager() as mgr:  
        print("Inside context")  

asyncio.run(main())  
```  

---

#### **12.6 Asynchronous Iterators (`async for`)**  
Iterate over asynchronous data streams.  
```python  
class AsyncIterator:  
    def __init__(self):  
        self.count = 0  

    def __aiter__(self):  
        return self  

    async def __anext__(self):  
        if self.count >= 3:  
            raise StopAsyncIteration  
        await asyncio.sleep(1)  
        self.count += 1  
        return self.count  

async def main():  
    async for num in AsyncIterator():  
        print(num)  # 1, 2, 3  

asyncio.run(main())  
```  

---

#### **12.7 Error Handling in Async Code**  
Handle exceptions in coroutines with `try/except`.  
```python  
async def error_task():  
    try:  
        await asyncio.sleep(1)  
        raise ValueError("Something went wrong!")  
    except ValueError as e:  
        print(f"Caught error: {e}")  

asyncio.run(error_task())  
```  

---

#### **12.8 Synchronization Primitives**  
Use **locks** to prevent race conditions.  
```python  
async def worker(lock, name):  
    async with lock:  
        print(f"{name} acquired the lock")  
        await asyncio.sleep(1)  

async def main():  
    lock = asyncio.Lock()  
    await asyncio.gather(  
        worker(lock, "Task 1"),  
        worker(lock, "Task 2")  
    )  

asyncio.run(main())  
```  

---

#### **12.9 Asynchronous Queues**  
Coordinate producers and consumers with `asyncio.Queue`.  
```python  
async def producer(queue):  
    for i in range(3):  
        await queue.put(i)  
        await asyncio.sleep(0.5)  

async def consumer(queue):  
    while True:  
        item = await queue.get()  
        print(f"Consumed {item}")  
        queue.task_done()  

async def main():  
    queue = asyncio.Queue()  
    await asyncio.gather(producer(queue), consumer(queue))  

asyncio.run(main())  
```  

---

#### **12.10 Integrating Blocking Code**  
Run blocking functions in a thread pool with `run_in_executor`.  
```python  
import time  

def blocking_task():  
    time.sleep(2)  
    return "Blocking task done"  

async def main():  
    loop = asyncio.get_running_loop()  
    result = await loop.run_in_executor(None, blocking_task)  
    print(result)  

asyncio.run(main())  
```  

---

#### **12.11 Asynchronous Subprocesses**  
Execute shell commands asynchronously.  
```python  
async def run_command():  
    proc = await asyncio.create_subprocess_shell(  
        "echo 'Hello'",  
        stdout=asyncio.subprocess.PIPE  
    )  
    stdout, _ = await proc.communicate()  
    print(stdout.decode().strip())  # "Hello"  

asyncio.run(run_command())  
```  

---

### **Key Notes**  
- **Concurrency vs. Parallelism**: Asyncio handles I/O-bound tasks concurrently in a single thread.  
- **Avoid Blocking Calls**: Use asynchronous libraries (e.g., `aiohttp`, `aiomysql`) for I/O operations.  
- **Version Compatibility**: Requires Python 3.7+ for `asyncio.run()` and modern syntax.  

---

### **13. Type Hints**  
Type hints improve code readability and enable static type checking (e.g., with `mypy`).  

---

#### **13.1 Variable Annotations**  
Declare types for variables using `: <Type>`.  
```python  
name: str = "Alice"  
age: int = 30  
is_valid: bool = True  
```  

---

#### **13.2 Function Annotations**  
Specify parameter and return types in functions.  
```python  
def greet(name: str) -> str:  
    return f"Hello, {name}"  

def add(a: int, b: int) -> int:  
    return a + b  
```  

---

#### **13.3 Basic Types from `typing`**  
Use `List`, `Dict`, `Tuple`, `Union`, `Optional`, etc., for complex types.  
```python  
from typing import List, Dict, Union, Optional  

# List of integers  
numbers: List[int] = [1, 2, 3]  

# Dictionary with string keys and float values  
prices: Dict[str, float] = {"apple": 1.99, "banana": 0.99}  

# Function returning a string or None  
def find_user(id: int) -> Optional[str]:  
    return "Alice" if id == 1 else None  

# Union of types  
result: Union[int, str] = 42  
```  

---

#### **13.4 Type Aliases**  
Simplify complex type signatures.  
```python  
from typing import List, Tuple  

# Alias for a 2D point  
Point = Tuple[float, float]  
polygon: List[Point] = [(0.0, 0.0), (1.0, 2.0)]  
```  

---

#### **13.5 Generics**  
Parameterize types with `Generic` and `TypeVar`.  
```python  
from typing import TypeVar, Generic, List  

T = TypeVar('T')  

class Stack(Generic[T]):  
    def __init__(self) -> None:  
        self.items: List[T] = []  

    def push(self, item: T) -> None:  
        self.items.append(item)  

# Usage  
int_stack: Stack[int] = Stack()  
int_stack.push(10)  
```  

---

#### **13.6 New Features in Python 3.10+**  
**Union Operator `|`**:  
```python  
def process(data: int | str) -> None:  
    pass  
```  

**Explicit `TypeAlias`**:  
```python  
from typing import TypeAlias  

Vector: TypeAlias = list[float]  
```  

---

#### **13.7 Type Checking with `mypy`**  
Install `mypy` and run:  
```bash  
mypy your_script.py  
```  

---

#### **13.8 Class and Method Annotations**  
Annotate instance variables and methods.  
```python  
class User:  
    def __init__(self, name: str, age: int) -> None:  
        self.name = name  
        self.age = age  

    def get_details(self) -> str:  
        return f"{self.name}, {self.age}"  
```  

---

#### **13.9 `@overload` for Multiple Signatures**  
Define multiple type signatures for a function.  
```python  
from typing import overload  

@overload  
def double(x: int) -> int: ...  

@overload  
def double(x: str) -> str: ...  

def double(x):  
    return x * 2  
```  

---

#### **13.10 Protocols (Structural Subtyping)**  
Define interfaces using `Protocol`.  
```python  
from typing import Protocol  

class Flyer(Protocol):  
    def fly(self) -> str: ...  

class Bird:  
    def fly(self) -> str:  
        return "Flying!"  

def make_it_fly(f: Flyer) -> None:  
    print(f.fly())  

bird = Bird()  
make_it_fly(bird)  # Valid  
```  

---

#### **13.11 Asynchronous Type Hints**  
Annotate coroutines with `Awaitable`.  
```python  
from typing import Awaitable  
import asyncio  

async def fetch() -> str:  
    return "Data"  

coro: Awaitable[str] = fetch()  
```  

---

#### **13.12 `Any` and Type Casting**  
**`Any`**: Opt out of type checking.  
```python  
from typing import Any  

data: Any = 42  
```  

**`cast()`**: Force a type when inference fails.  
```python  
from typing import cast  

value = cast(int, "123")  # Treat "123" as int (use cautiously)  
```  

---

#### **13.13 `NewType` for Distinct Types**  
Create distinct types for clarity.  
```python  
from typing import NewType  

UserId = NewType('UserId', int)  
user_id = UserId(1001)  
```  

---

#### **13.14 `Literal` and `Final`**  
**`Literal`**: Restrict to specific values.  
```python  
from typing import Literal  

Mode = Literal["read", "write"]  
current_mode: Mode = "read"  
```  

**`Final`**: Declare constants.  
```python  
from typing import Final  

MAX_SIZE: Final[int] = 100  
```  

---

#### **13.15 `TypedDict` for Structured Dictionaries**  
Type-check dictionaries with specific keys.  
```python  
from typing import TypedDict  

class Person(TypedDict):  
    name: str  
    age: int  

user: Person = {"name": "Alice", "age": 30}  
```  

---

#### **13.16 `@dataclass` Integration**  
Combine type hints with data classes.  
```python  
from dataclasses import dataclass  

@dataclass  
class Product:  
    name: str  
    price: float  
    in_stock: bool = True  

item = Product("Laptop", 999.99)  
```  

---

### **Key Notes**  
- **Runtime Impact**: Type hints are ignored at runtime (use `__annotations__` to access them).  
- **Gradual Typing**: Mix typed and untyped code.  
- **Best Practices**: Use precise types, avoid `Any`, and leverage `mypy` for checks.

---

### **14. Special Keywords**

#### **14.1 Control Flow Keywords (`if`, `else`, `elif`)**  
Used for conditional execution.  
```python  
if x > 0:  
    print("Positive")  
elif x == 0:  
    print("Zero")  
else:  
    print("Negative")  
```  

---

#### **14.2 Loop Keywords (`for`, `while`, `break`, `continue`)**  
Iterate over sequences or repeat code blocks.  
```python  
for i in range(3):  
    if i == 1:  
        continue  # Skip iteration  
    print(i)      # 0, 2  

while True:  
    break  # Exit loop immediately  
```  

---

#### **14.3 Function and Class Keywords (`def`, `return`, `class`, `lambda`)**  
Define functions, classes, and anonymous functions.  
```python  
def greet(name):  
    return f"Hello, {name}"  

class Dog:  
    pass  

square = lambda x: x ** 2  
```  

---

#### **14.4 Error Handling Keywords (`try`, `except`, `finally`, `raise`)**  
Handle and propagate exceptions.  
```python  
try:  
    raise ValueError("Oops!")  
except ValueError as e:  
    print(e)  
finally:  
    print("Cleanup")  
```  

---

#### **14.5 Logical Operators (`and`, `or`, `not`)**  
Combine boolean expressions.  
```python  
if x > 0 and x < 10:  
    print("Valid")  

is_valid = not False  # True  
```  

---

#### **14.6 Membership and Identity Keywords (`in`, `is`)**  
Check membership or object identity.  
```python  
if "a" in "apple":  
    print("Found")  

a = [1, 2]  
b = a  
print(a is b)  # True (same object)  
```  

---

#### **14.7 Scope Keywords (`global`, `nonlocal`)**  
Modify variable scope.  
```python  
x = 10  
def update():  
    global x  
    x = 20  

def outer():  
    count = 0  
    def inner():  
        nonlocal count  
        count += 1  
```  

---

#### **14.8 Asynchronous Keywords (`async`, `await`)**  
Define and manage coroutines.  
```python  
async def fetch():  
    await asyncio.sleep(1)  
```  

---

#### **14.9 Placeholder and Deletion Keywords (`pass`, `del`)**  
**`pass`**: Empty code block placeholder.  
```python  
if x > 0:  
    pass  # Do nothing  
```  

**`del`**: Delete objects or variables.  
```python  
my_list = [1, 2, 3]  
del my_list[0]  # [2, 3]  
```  

---

#### **14.10 Context Management Keyword (`with`)**  
Manage resources (e.g., files).  
```python  
with open("file.txt", "r") as file:  
    content = file.read()  
```  

---

#### **14.11 Debugging Keyword (`assert`)**  
Check conditions during debugging.  
```python  
assert x > 0, "x must be positive"  
```  

---

#### **14.12 Generator Keyword (`yield`)**  
Create generator functions.  
```python  
def count_up(n):  
    i = 0  
    while i < n:  
        yield i  
        i += 1  
```  

---

#### **14.13 Literal Keywords (`True`, `False`, `None`)**  
Boolean and null values.  
```python  
is_valid = True  
result = None  # Represents "no value"  
```  

---

### **Key Notes**  
- **Reserved Words**: Keywords cannot be used as variable/function names.  
- **Immutability**: `True`, `False`, and `None` are singleton objects.  
- **Context Managers**: Use `with` for automatic resource cleanup (e.g., files, locks).  

---

This list covers **core Python syntax** for variables, control flow, functions, data structures, OOP, and advanced features. For full documentation, refer to the [Python Official Docs](https://docs.python.org/3/).
