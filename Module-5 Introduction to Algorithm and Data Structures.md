Great! Let's dive into **Introduction to Algorithm and Data Structures** for Python, covering all the topics you've mentioned with explanations and code examples.

---

## ⏳ **1. Time Complexity**

Time complexity measures how the running time of an algorithm increases as the size of the input increases. It's often expressed using **Big O notation**.

### Common Time Complexities:

- **O(1)** – Constant time
- **O(log n)** – Logarithmic time
- **O(n)** – Linear time
- **O(n^2)** – Quadratic time

#### Example: Time Complexity of Linear Search
```python
def linear_search(arr, target):
    for i in range(len(arr)):  # O(n)
        if arr[i] == target:
            return i
    return -1

# Example of usage
arr = [1, 2, 3, 4, 5]
print(linear_search(arr, 3))  # Output: 2
```

#### Example: Time Complexity of Binary Search
```python
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:  # O(log n)
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1

# Example of usage
arr = [1, 2, 3, 4, 5]
print(binary_search(arr, 3))  # Output: 2
```

---

## 📦 **2. Space Complexity**

Space complexity measures the amount of memory an algorithm uses relative to the input size.

- **O(1)** – Constant space (does not depend on input size)
- **O(n)** – Linear space (space grows with input size)

#### Example: Space Complexity of a List
```python
def create_list(n):
    lst = []
    for i in range(n):
        lst.append(i)
    return lst

# Space complexity is O(n) because it stores the list
print(create_list(5))
```

---

## 🔄 **3. Sorting Algorithms**

Sorting algorithms arrange data in a specific order (ascending or descending).

### 1. **Bubble Sort (O(n^2))**

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

arr = [64, 25, 12, 22, 11]
bubble_sort(arr)
print("Sorted array:", arr)
```

### 2. **Merge Sort (O(n log n))**

```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left = arr[:mid]
        right = arr[mid:]

        merge_sort(left)
        merge_sort(right)

        i = j = k = 0
        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                arr[k] = left[i]
                i += 1
            else:
                arr[k] = right[j]
                j += 1
            k += 1

        while i < len(left):
            arr[k] = left[i]
            i += 1
            k += 1

        while j < len(right):
            arr[k] = right[j]
            j += 1
            k += 1

arr = [64, 25, 12, 22, 11]
merge_sort(arr)
print("Sorted array:", arr)
```

---

## 🔗 **4. Linked List**

A linked list is a linear data structure where each element (node) points to the next element.

### **Node Definition**
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# Create nodes
node1 = Node(10)
node2 = Node(20)
node3 = Node(30)

# Link nodes
node1.next = node2
node2.next = node3

# Traverse the list
current = node1
while current:
    print(current.data)
    current = current.next
```

---

## 📜 **5. Stack**

A stack is a collection that follows the **LIFO (Last In First Out)** principle.

### Stack Implementation:
```python
class Stack:
    def __init__(self):
        self.stack = []

    def push(self, item):
        self.stack.append(item)

    def pop(self):
        if not self.is_empty():
            return self.stack.pop()

    def peek(self):
        if not self.is_empty():
            return self.stack[-1]

    def is_empty(self):
        return len(self.stack) == 0

# Example of stack usage
stack = Stack()
stack.push(10)
stack.push(20)
stack.push(30)

print(stack.pop())  # 30
print(stack.peek())  # 20
```

---

## 🧭 **6. Queue**

A queue is a collection that follows the **FIFO (First In First Out)** principle.

### Queue Implementation:

```python
class Queue:
    def __init__(self):
        self.queue = []

    def enqueue(self, item):
        self.queue.append(item)

    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)

    def is_empty(self):
        return len(self.queue) == 0

    def peek(self):
        if not self.is_empty():
            return self.queue[0]

# Example of queue usage
queue = Queue()
queue.enqueue(10)
queue.enqueue(20)
queue.enqueue(30)

print(queue.dequeue())  # 10
print(queue.peek())     # 20
```

---

## 🧩 **7. Problem-Solving Session**

Let's solve coding challenges using stack, queue, and linked list.

### Problem 1: Reverse a Stack

```python
def reverse_stack(stack):
    if stack.is_empty():
        return
    temp = stack.pop()
    reverse_stack(stack)
    stack.push(temp)

# Example usage:
stack = Stack()
stack.push(1)
stack.push(2)
stack.push(3)

reverse_stack(stack)
while not stack.is_empty():
    print(stack.pop())
```

### Problem 2: Implement a Queue using Two Stacks

```python
class QueueUsingStacks:
    def __init__(self):
        self.stack1 = Stack()
        self.stack2 = Stack()

    def enqueue(self, item):
        self.stack1.push(item)

    def dequeue(self):
        if self.stack2.is_empty():
            while not self.stack1.is_empty():
                self.stack2.push(self.stack1.pop())
        return self.stack2.pop()

# Example usage:
queue = QueueUsingStacks()
queue.enqueue(1)
queue.enqueue(2)
queue.enqueue(3)

print(queue.dequeue())  # 1
print(queue.dequeue())  # 2
```

---

## 📚 **Q&A Session**

Let me know if you have any questions or need further clarification on any concepts, such as how to optimize these structures, the best use cases, or real-world applications of algorithms!

---

Feel free to solve some challenges on your own, and I can help review or offer hints!