Let's dive into **Object-Oriented Programming (OOP)** in Python! This will be a 5-hour lesson covering key OOP concepts, including examples and problem-solving sessions.

---

## 🏁 **1. Concepts of Classes and Objects**

### What are Classes and Objects?
- **Class**: A blueprint for creating objects.
- **Object**: An instance of a class.

### Example: Simple Class and Object

```python
# Define a class
class Person:
    def __init__(self, name, age):
        self.name = name  # instance variable
        self.age = age    # instance variable

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")

# Create an object (instance) of the Person class
person1 = Person("Alice", 30)
person2 = Person("Bob", 25)

# Call a method on the object
person1.greet()  # Output: Hello, my name is Alice and I am 30 years old.
person2.greet()  # Output: Hello, my name is Bob and I am 25 years old.
```

---

## 🧬 **2. Inheritance and Polymorphism**

### Inheritance
Inheritance allows a class (child class) to inherit methods and attributes from another class (parent class).

```python
# Parent class (Base class)
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        print(f"{self.name} makes a sound")

# Child class (Derived class)
class Dog(Animal):
    def speak(self):
        print(f"{self.name} barks")

# Child class (Derived class)
class Cat(Animal):
    def speak(self):
        print(f"{self.name} meows")

# Creating objects of the child classes
dog = Dog("Rex")
cat = Cat("Whiskers")

dog.speak()  # Output: Rex barks
cat.speak()  # Output: Whiskers meows
```

### Polymorphism
Polymorphism allows a method to behave differently based on the object calling it. This is achieved by overriding methods in child classes.

---

## 🔒 **3. Encapsulation and Abstraction**

### Encapsulation
Encapsulation is the bundling of data and methods that operate on the data into a single unit or class. It helps protect the internal state of an object.

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.__balance = balance  # Private attribute

    def deposit(self, amount):
        self.__balance += amount

    def withdraw(self, amount):
        if amount > self.__balance:
            print("Insufficient funds!")
        else:
            self.__balance -= amount

    def get_balance(self):
        return self.__balance

# Usage
account = BankAccount("Alice", 1000)
account.deposit(500)
account.withdraw(200)
print(account.get_balance())  # Output: 1300
```

### Abstraction
Abstraction hides the complex implementation details and exposes only necessary functionality.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

# Usage
rect = Rectangle(5, 10)
print(rect.area())  # Output: 50
```

---

## ⚠️ **4. Introduction to Exceptions**

Exceptions are errors that occur during the execution of a program. They can be caught and handled to prevent the program from crashing.

### Example: Basic Exception Handling

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
    print(f"Result: {result}")
except ZeroDivisionError:
    print("Error: Cannot divide by zero!")
except ValueError:
    print("Error: Invalid input! Please enter a number.")
```

---

## 🛠 **5. Different Kinds of Exception Handling**

### Multiple Exceptions

```python
try:
    num1 = int(input("Enter first number: "))
    num2 = int(input("Enter second number: "))
    result = num1 / num2
    print(f"Result: {result}")
except ZeroDivisionError:
    print("Cannot divide by zero!")
except ValueError:
    print("Invalid input! Please enter valid integers.")
```

### Custom Exception

```python
class NegativeAmountError(Exception):
    pass

class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.balance = balance

    def deposit(self, amount):
        if amount < 0:
            raise NegativeAmountError("Deposit amount cannot be negative!")
        self.balance += amount

    def get_balance(self):
        return self.balance

# Usage
account = BankAccount("Alice")
try:
    account.deposit(-100)
except NegativeAmountError as e:
    print(e)  # Output: Deposit amount cannot be negative!
```

---

## 🏦 **6. Class Condition: Develop a Simple Object-Oriented Program (Basic Banking System)**

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.__balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"{amount} deposited successfully!")
        else:
            print("Deposit amount should be positive!")

    def withdraw(self, amount):
        if amount <= 0:
            print("Withdrawal amount should be positive!")
        elif amount > self.__balance:
            print("Insufficient funds!")
        else:
            self.__balance -= amount
            print(f"{amount} withdrawn successfully!")

    def get_balance(self):
        return self.__balance

    def display_account(self):
        print(f"Account owner: {self.owner}")
        print(f"Account balance: {self.__balance}")

# Usage
account = BankAccount("Alice", 1000)
account.display_account()

account.deposit(500)
account.withdraw(200)
account.display_account()

account.withdraw(2000)  # Insufficient funds!
```

---

## 🧩 **7. Problem-Solving Session**

Let's solve a couple of OOP-related problems.

### Problem 1: Inheritance and Method Overriding

Create a `Vehicle` class and derive `Car` and `Bike` classes from it. Override the `start_engine()` method for each.

```python
class Vehicle:
    def start_engine(self):
        print("Starting engine...")

class Car(Vehicle):
    def start_engine(self):
        print("Starting car engine...")

class Bike(Vehicle):
    def start_engine(self):
        print("Starting bike engine...")

# Test the classes
car = Car()
car.start_engine()  # Output: Starting car engine...

bike = Bike()
bike.start_engine()  # Output: Starting bike engine...
```

### Problem 2: Implementing a Simple Bank System

Create a `Bank` class with methods for account creation, deposit, and withdrawal.

```python
class Bank:
    def __init__(self):
        self.accounts = {}

    def create_account(self, account_number, initial_balance=0):
        self.accounts[account_number] = BankAccount(account_number, initial_balance)

    def deposit(self, account_number, amount):
        if account_number in self.accounts:
            self.accounts[account_number].deposit(amount)
        else:
            print(f"Account {account_number} not found!")

    def withdraw(self, account_number, amount):
        if account_number in self.accounts:
            self.accounts[account_number].withdraw(amount)
        else:
            print(f"Account {account_number} not found!")

# Usage
bank = Bank()
bank.create_account("12345", 1000)
bank.deposit("12345", 500)
bank.withdraw("12345", 300)
```

---

## 📚 **Q&A Session**

Feel free to ask any questions about these topics or to clarify any code examples. You can also try solving more problems, and I’ll be happy to assist!