---
title: "Object-Oriented Programming(OOP) in Python 101"
seoTitle: "Object-Oriented Programming(OOP) in Python 101"
datePublished: Mon Jan 30 2023 07:50:46 GMT+0000 (Coordinated Universal Time)
cuid: cldiih9ms000c09l2bn9r28ff
slug: object-oriented-programmingoop-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/Agx5_TLsIf4/upload/0162967cdfad4f24e591c3a7db1935d5.jpeg
tags: oop, programming-blogs, python, python3, python-beginner

---

Object-oriented programming (OOP) is a programming paradigm that uses objects and their interactions to design applications and computer programs. Python, being a high-level programming language, supports OOP and provides several features to implement it. In this tutorial, we will cover the following topics to help you understand OOP in Python:

### Class and Object

A class is a blueprint for creating objects (a particular data structure), providing initial values for state (member variables or attributes), and implementations of behavior (member functions or methods). An object is an instance of a class. For example, a class "Car" can have attributes like "make", "model", and "year" and methods like "start", "stop", and "drive".

### Creating a Class

A class is defined using the class keyword, followed by the class name and a colon. The class block is indented, and all the class members (variables and methods) are defined within this block.

```python
class Car:
    make = ""
    model = ""
    year = 0
    def start(self):
        print("Car started")
    def stop(self):
        print("Car stopped")
```

### Creating an Object

An object is created by calling the class name as if it were a function.

```python
my_car = Car()
```

### Accessing Attributes

Attributes are accessed using the dot notation.

```python
my_car.make = "Toyota"
my_car.model = "Camry"
my_car.year = 2020
```

### Accessing Methods

Methods are accessed using the dot notation.

```python
my_car.start() #Car started
my_car.stop() #Car stopped
```

### Constructors

In Python, constructors are special methods automatically called when an object is created. The method name is **init**.

```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
```

### Inheritance

Inheritance is a mechanism that allows a new class to inherit properties and methods from an existing class. The new class is called a derived class, and the existing class is called a base class.

```python
class ElectricCar(Car):
    def __init__(self, make, model, year):
        Car.__init__(self, make, model, year)
```

### Polymorphism

Polymorphism is a feature that allows objects of different classes to be treated as objects of a common base class. In Python, polymorphism is achieved through function overloading and operator overloading.

```python
def start(car):
    car.start()

my_car = Car()
my_electric_car = ElectricCar()

start(my_car)
start(my_electric_car)
```

### Encapsulation

Encapsulation is a technique that restricts direct access to an object's internal state and methods. In Python, encapsulation is achieved through the use of private and protected members. To define private members, we use a single underscore before the name. To define protected members, we use a double underscore before the name. However, It's worth noting that the use of the single underscore before the name of an attribute or method does not make it truly private in Python. Instead, it's a convention that indicates that the attribute or method should not be accessed directly from outside the class. It's also worth noting that to make a member truly private in Python, you can use a double underscore before the name, this will cause name mangling, which changes the name of the attribute or method to be prefixed with \_ClassName, this is done to avoid naming conflicts when subclassing.

```python
class Car:
    def __init__(self, make, model, year):
        self.__make = make
        self.__model = model
        self.__year = year
```

This way, you can access the attribute like this :

```python
my_car = Car("Toyota", "Camry", 2020)
print(my_car._Car__make) # "Toyota"
```

This is a way to implement encapsulation in Python but it's not widely used. In most cases, developers rely on naming conventions to indicate that an attribute or method should be treated as private, and leave it up to the user to respect these conventions.

Another way to implement encapsulation in Python is to use properties. Properties allow you to define getter and setter methods for an attribute, which can be used to control access to the attribute.

```python
class Car:
    def __init__(self, make, model, year):
        self._make = make
        self._model = model
        self._year = year
        
    @property
    def make(self):
        return self._make
    
    @make.setter
    def make(self, value):
        self._make = value
```

This way, you can access the attribute like this:

```python
my_car = Car("Toyota", "Camry", 2020)
print(my_car.make) # "Toyota"
my_car.make = "Honda"
```

By using the property decorator, you can control what happens when the attribute is accessed or modified. For example, you can add validation checks, or update other attributes based on the value being set.

In addition to the above, you can use the @property decorator to define read-only attributes, you can do this by only defining a getter method without the setter method,

```python
class Car:
    def __init__(self, make, model, year):
        self._make = make
        self._model = model
        self._year = year
        
    @property
    def full_name(self):
        return f'{self._make} {self._model}'
```

This way, you can access the attribute like this:

```python
my_car = Car("Toyota", "Camry", 2020)
print(my_car.full_name) # "Toyota Camry"
my_car.full_name = "Honda Civic"
```

This will raise an error because the attribute is read-only.

In conclusion, encapsulation in Python can be achieved through naming conventions, properties, and name mangling, it's up to the developer to decide which method to use based on the requirements and the conventions of the project.

### Coding Project

Create a simple inventory management system. This project would cover several key concepts, such as object-oriented programming, file I/O, and data manipulation. Here are the requirements for the project:

1. Create a class for the inventory item, with the following attributes: name, quantity, and price.
    
2. Create a class for the inventory management system, with the following methods:
    
    * add\_item: allows the user to add a new item to the inventory
        
    * remove\_item: allows the user to remove an item from the inventory
        
    * update\_item: allows the user to update the quantity or price of an item
        
    * display\_inventory: displays the current inventory
        
3. Allow the user to load and save the inventory from/to a CSV file
    
4. Create a simple UI that allows the user to interact with the inventory management system through a menu.
    

This project would be a great opportunity for you to practice and solidify your understanding of OOP concepts, data manipulation, and file I/O. Additionally, the project will be a great opportunity for you to learn about the best practices for building a simple user interface, which is an essential part of software development.

Happy hacking!

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)