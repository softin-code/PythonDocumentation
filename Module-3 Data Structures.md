Perfect! Here's a full Python **Data Structures** lesson with explanations and **examples** for each topic. Let’s go step by step.

---

## 🔹 **1. Lists**

A list is an ordered, mutable (changeable) collection.

```python
fruits = ['apple', 'banana', 'cherry']
print(fruits[0])  # apple
```

---

## 🔹 **2. List Methods**

```python
fruits.append('orange')       # Add item
fruits.insert(1, 'grape')     # Insert at index
fruits.remove('banana')       # Remove item
fruits.pop()                  # Remove last item
fruits.sort()                 # Sort list
fruits.reverse()              # Reverse list
print(len(fruits))            # Length of list
```

---

## 🔹 **3. List Comprehension**

```python
squares = [x**2 for x in range(5)]
print(squares)  # [0, 1, 4, 9, 16]
```

With condition:

```python
even = [x for x in range(10) if x % 2 == 0]
print(even)  # [0, 2, 4, 6, 8]
```

---

## 🔹 **4. List Manipulation**

```python
fruits = ['apple', 'banana']
fruits[0] = 'mango'      # Replace element
fruits += ['grape']      # Add more
print(fruits[1:])        # Slicing: from index 1
del fruits[1]            # Delete by index
print(fruits)
```

---

## 🔹 **5. Tuples**

Immutable (unchangeable) ordered collection.

```python
point = (3, 4)
print(point[0])  # 3
```

---

## 🔹 **6. Tuple Methods**

```python
nums = (1, 2, 2, 3)
print(nums.count(2))  # 2
print(nums.index(3))  # 3
```

---

## 🔹 **7. Generators**

Efficient way to iterate lazily.

```python
def count_up_to(n):
    i = 1
    while i <= n:
        yield i
        i += 1

for num in count_up_to(3):
    print(num)
```

---

## 🔹 **8. Sets and Set Methods**

Unordered, no duplicates.

```python
my_set = {1, 2, 3, 3}
my_set.add(4)
my_set.update([5, 6])
my_set.discard(2)
print(my_set)
```

Common methods:

```python
a = {1, 2, 3}
b = {3, 4, 5}
print(a.union(b))         # {1, 2, 3, 4, 5}
print(a.intersection(b))  # {3}
print(a.difference(b))    # {1, 2}
```

---

## 🔹 **9. Frozen Set**

Immutable set.

```python
fs = frozenset([1, 2, 3])
# fs.add(4)  ❌ will raise AttributeError
print(fs)
```

---

## 🔹 **10. Dictionaries**

Key-value pairs.

```python
person = {'name': 'Alice', 'age': 30}
print(person['name'])  # Alice
```

---

## 🔹 **11. Dict Methods**

```python
person['age'] = 31              # Update value
person['city'] = 'New York'     # Add new key
person.pop('city')              # Remove key
print(person.keys())            # dict_keys(['name', 'age'])
print(person.values())          # dict_values(['Alice', 31])
print(person.items())           # dict_items([('name', 'Alice'), ('age', 31)])
```

---

## 🔹 **12. String Manipulation and Formatting**

```python
s = "hello world"
print(s.upper())           # HELLO WORLD
print(s.title())           # Hello World
print(s.replace("world", "Python"))  # hello Python
print("Python" in s)       # False

name = "Alice"
age = 30
print(f"My name is {name} and I'm {age} years old.")  # f-string
```

---

## 🧩 **13. Problem-Solving Practice**

You can try solving these:

1. Create a list of even numbers from 1 to 20 using list comprehension.
2. Write a function that counts how many times each character appears in a string using a dictionary.
3. Create a generator that yields square numbers up to `n`.
4. Make a set from a list of numbers with duplicates.
5. Use a dictionary to store and display student name & grade pairs.

---

Let me know if you'd like to work on these problems together, or if you want a quiz or challenge based on this content!