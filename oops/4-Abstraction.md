
# Abstraction Challenges

---

## Challenge 1: Basic Abstraction (Shape)

**Question:**

Create an abstract class `Shape` with an abstract method `area()`.

Create two child classes:

- `Rectangle` → has `length` and `breadth`
- `Circle` → has `radius`

Both classes should implement the `area()` method.

Create objects of both classes and print their areas.

### Code:

```python
from abc import ABC, abstractmethod
import math


class Shape(ABC):
    @abstractmethod
    def area(self):
        pass


class Rectangle(Shape):
    def __init__(self, length, breadth):
        self.length = length
        self.breadth = breadth

    def area(self):
        return self.length * self.breadth


class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return math.pi * self.radius * self.radius


# Creating objects
r = Rectangle(10, 5)
c = Circle(7)

print("Area of Rectangle:", r.area())
print("Area of Circle:", round(c.area(), 2))
```

### Expected Output:

```text
Area of Rectangle: 50
Area of Circle: 153.94
```

---

## Challenge 2: Abstraction with Payment System

**Question:**

Create an abstract class `Payment` with an abstract method `pay()`.

Create two child classes:

- `CreditCardPayment`
- `UPIPayment`

Both classes should implement the `pay()` method with different messages.

Create objects and call the `pay()` method.

### Code:

```python
from abc import ABC, abstractmethod


class Payment(ABC):
    @abstractmethod
    def pay(self, amount):
        pass


class CreditCardPayment(Payment):
    def pay(self, amount):
        print(f"Paid ₹{amount} using Credit Card")


class UPIPayment(Payment):
    def pay(self, amount):
        print(f"Paid ₹{amount} using UPI")


# Creating objects
credit = CreditCardPayment()
upi = UPIPayment()

credit.pay(1500)
upi.pay(800)
```

### Expected Output:

```text
Paid ₹1500 using Credit Card
Paid ₹800 using UPI
```

---

## Challenge 3: Abstraction with Animal Sound

**Question:**

Create an abstract class `Animal` with an abstract method `make_sound()`.

Create three child classes:

- `Dog`
- `Cat`
- `Cow`

Each class should implement the `make_sound()` method.

Create objects and call the method for each animal.

### Code:

```python
from abc import ABC, abstractmethod


class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass


class Dog(Animal):
    def make_sound(self):
        print("Dog barks")


class Cat(Animal):
    def make_sound(self):
        print("Cat meows")


class Cow(Animal):
    def make_sound(self):
        print("Cow moos")


# Creating objects
d = Dog()
c = Cat()
cw = Cow()

d.make_sound()
c.make_sound()
cw.make_sound()
```

### Expected Output:

```text
Dog barks
Cat meows
Cow moos
```
