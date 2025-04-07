Sure! Here's your **Python: Debugging and Unit Testing (4 Hours)** learning module with **examples for every topic**:

---

## 🐞 1. Introduction to Debugging Techniques

### ✅ Bug vs Error

**Bug**: A flaw in logic that gives unexpected output.  
**Error**: A runtime or syntax issue.

---

### Example: Syntax Error vs Logic Bug

```python
# Syntax Error
# print("Hello"  # missing closing parenthesis

# Logic Bug
def add(a, b):
    return a - b  # Bug: should be a + b

print(add(2, 3))  # Output: -1 (wrong)
```

---

### 🛠️ Debugging Tools

#### Using `print()` for Debugging

```python
def find_max(numbers):
    max_val = numbers[0]
    for num in numbers:
        print("Checking:", num)
        if num > max_val:
            max_val = num
    return max_val

print(find_max([1, 5, 2, 8]))
```

#### Using `pdb` (Python Debugger)

```python
import pdb

def buggy_add(a, b):
    pdb.set_trace()  # Breakpoint
    result = a + b
    return result

print(buggy_add(5, 6))
```

> Commands in `pdb`: `n` (next), `c` (continue), `q` (quit), `p` (print), `l` (list)

---

## ✅ 2. Introduction to Unit Testing

- Unit testing ensures each small "unit" of your code works as expected.
- Python provides a built-in module called `unittest`.

---

## 🧪 3. Python Testing Framework

### Example: Creating a Test Case

```python
import unittest

def multiply(x, y):
    return x * y

class TestMath(unittest.TestCase):
    def test_multiply(self):
        self.assertEqual(multiply(3, 4), 12)
        self.assertEqual(multiply(-1, 5), -5)

if __name__ == '__main__':
    unittest.main()
```

> Save as `test_math.py` and run:  
```bash
python test_math.py
```

---

## 🏃 4. Writing and Running Tests

### Test Various Cases

```python
import unittest

def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b

class TestDivide(unittest.TestCase):
    def test_divide_normal(self):
        self.assertEqual(divide(10, 2), 5)

    def test_divide_zero(self):
        with self.assertRaises(ValueError):
            divide(10, 0)

if __name__ == '__main__':
    unittest.main()
```

---

## 🧰 5. Mocking and Patching

When a function depends on external resources (e.g., databases, APIs), we mock them.

### Example: Mocking a Function

```python
from unittest.mock import patch
import unittest

def get_user_name():
    # Imagine this calls an API
    return "real_user"

class TestMocking(unittest.TestCase):
    @patch('__main__.get_user_name', return_value='mocked_user')
    def test_mock_user(self, mock_func):
        self.assertEqual(get_user_name(), 'mocked_user')

if __name__ == '__main__':
    unittest.main()
```

---

### Example: Patching a Method Inside a Class

```python
from unittest.mock import patch
import unittest

class Auth:
    def get_user(self):
        return "Real User"

class TestAuth(unittest.TestCase):
    @patch.object(Auth, 'get_user', return_value='Mock User')
    def test_get_user(self, mock_method):
        auth = Auth()
        self.assertEqual(auth.get_user(), 'Mock User')

if __name__ == '__main__':
    unittest.main()
```

---

## 🧩 6. Unit Testing Exercises

### ✅ Exercise 1: Test Calculator

```python
def add(a, b): return a + b
def subtract(a, b): return a - b

import unittest

class TestCalc(unittest.TestCase):
    def test_add(self): self.assertEqual(add(2, 3), 5)
    def test_subtract(self): self.assertEqual(subtract(5, 2), 3)

if __name__ == '__main__':
    unittest.main()
```

---

### ✅ Exercise 2: Validate Email (with test)

```python
import re

def is_valid_email(email):
    return re.match(r"[^@]+@[^@]+\.[^@]+", email) is not None

class TestEmail(unittest.TestCase):
    def test_valid(self):
        self.assertTrue(is_valid_email("test@example.com"))
    def test_invalid(self):
        self.assertFalse(is_valid_email("invalid-email"))

if __name__ == '__main__':
    unittest.main()
```

---

### ✅ Exercise 3: Mock API Call

```python
import unittest
from unittest.mock import patch

def fetch_data():
    # Simulate network/API call
    return {"data": "real"}

class TestFetch(unittest.TestCase):
    @patch('__main__.fetch_data', return_value={"data": "mocked"})
    def test_fetch(self, mock_fetch):
        result = fetch_data()
        self.assertEqual(result['data'], 'mocked')

if __name__ == '__main__':
    unittest.main()
```

---

Would you like a **real-world mini-project** with unit testing and file handling combined? I can guide you step-by-step!