
# Encapsulation Challenges

---

## Challenge 1: Basic Encapsulation

**Question:**

Create a class `BankAccount` with the following:

- Private attributes: `__account_number`, `__balance`
- Methods:
  - `deposit(amount)` → adds money to the balance
  - `withdraw(amount)` → deducts money only if sufficient balance is available
  - `get_balance()` → returns the current balance

**Rules:**

- Do not allow direct access to `__balance`.
- Show appropriate messages for deposit and withdraw.

Create an object and test the methods.

### Code:

```python
class BankAccount:
    def __init__(self, account_number, balance):
        self.__account_number = account_number
        self.__balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"Deposited: ₹{amount}")
        else:
            print("Invalid deposit amount")

    def withdraw(self, amount):
        if amount > 0 and amount <= self.__balance:
            self.__balance -= amount
            print(f"Withdrawn: ₹{amount}")
        else:
            print("Insufficient balance or invalid amount")

    def get_balance(self):
        return self.__balance


# Creating object
acc = BankAccount("ACC1001", 5000)

acc.deposit(2000)
acc.withdraw(1500)
print("Current Balance: ₹", acc.get_balance())
```

### Expected Output:

```text
Deposited: ₹2000
Withdrawn: ₹1500
Current Balance: ₹ 5500
```

---

## Challenge 2: Encapsulation with Student Marks

**Question:**

Create a class `Student` with the following:

- Private attribute: `__marks`
- Public attribute: `name`
- Methods:
  - `set_marks(marks)` → sets marks only if marks are between 0 and 100.
  - `get_marks()` → returns the marks.
  - `display()` → shows name and marks.

**Rules:**

- Marks should not be accessible directly.
- Only allow valid marks (0 to 100).

### Code:

```python
class Student:
    def __init__(self, name):
        self.name = name
        self.__marks = 0

    def set_marks(self, marks):
        if 0 <= marks <= 100:
            self.__marks = marks
            print("Marks updated successfully")
        else:
            print("Invalid marks! Please enter marks between 0 and 100")

    def get_marks(self):
        return self.__marks

    def display(self):
        print(f"Name: {self.name}, Marks: {self.__marks}")


# Creating object
s1 = Student("Rahul")

s1.set_marks(85)
s1.display()

s1.set_marks(120)   # Invalid
s1.display()
```

### Expected Output:

```text
Marks updated successfully
Name: Rahul, Marks: 85
Invalid marks! Please enter marks between 0 and 100
Name: Rahul, Marks: 85
```
