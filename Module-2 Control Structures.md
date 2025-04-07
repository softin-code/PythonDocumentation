Awesome! Let's dive into Python **Control Structures**. Here's how we can break down the 3-hour session:

---

## 🧠 **1. Conditional Statements (`if`, `elif`, `else`)**

### 🔹 Syntax:
```python
x = 10
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is exactly 5")
else:
    print("x is less than 5")
```

### 🔹 Notes:
- `if` is the initial condition.
- `elif` means "else if", and you can have multiple `elif`.
- `else` is the fallback if no condition is true.

---

## 🔁 **2. Loops**

### 🔸 `for` Loop (used to iterate over sequences like lists, strings, etc.)
```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

### 🔸 `while` Loop (runs while a condition is True)
```python
i = 1
while i <= 5:
    print(i)
    i += 1
```

---

## 🔀 **3. Control Flow & Decision Making**

### 🔸 `break` — exit the loop early:
```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

### 🔸 `continue` — skip current iteration:
```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

### 🔸 `pass` — do nothing (placeholder):
```python
if True:
    pass  # You can write the code later
```

---

## 🧩 **4. Problem-Solving Practice**

Here are 3 practice problems. Try them out, and I can review your solutions:

---

### ✅ Problem 1: Even or Odd Checker
Write a program that takes a number from the user and prints if it's even or odd.

---

### ✅ Problem 2: Multiplication Table
Use a `for` loop to print the multiplication table of 5 (up to 10).

---

### ✅ Problem 3: Sum of Numbers (While Loop)
Keep asking the user for numbers and add them until the user types "done".

---

Would you like to solve these now one by one with my help? Or prefer a quiz-style review after trying them yourself?