---
title: "Introduction to Python 101"
seoTitle: "Introduction to Python 101"
datePublished: Sat Feb 18 2023 11:10:29 GMT+0000 (Coordinated Universal Time)
cuid: cle9uzafd000a09lf4fi5088i
slug: introduction-to-python-101
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1676814602143/df3bb568-78cc-461b-87a3-2fb790bc2718.png
tags: programming-blogs, python, data-science, python3, python-beginner

---

## **Lesson 1: Introduction to Python**

Welcome to the Introduction to Python course! In this lesson, we will cover the basics of Python programming language.

### **Installing Python**

To get started, you need to install Python on your computer. You can download the latest version of Python from the official website ([**https://www.python.org/downloads/**](https://www.python.org/downloads/)). Follow the installation instructions for your operating system to complete the installation.

### **Python Interpreter**

Python code can be executed in two ways: in a script file or using the Python interpreter. The Python interpreter is an interactive shell that allows you to execute Python code on the fly. To start the Python interpreter, open a terminal window and type "python" without quotes. You should see the Python prompt "&gt;&gt;&gt;".

### **Basic Syntax**

Python code is written in a straightforward syntax that is easy to read and write. Here is an example of a Python program that prints "Hello, World!" to the console:

```python
print("Hello, World!")
```

### **Variables and Data Types**

Variables are used to store data in Python. In Python, you don't need to specify the data type of a variable - Python infers the type based on the value assigned to it. Here is an example of a Python program that uses variables:

```python
name = "John"
age = 30
height = 1.75
```

In this example, we have three variables: name, age, and height. The first variable is a string, the second is an integer, and the third is a float.

### **Control Structures**

Python has several control structures that allow you to control the flow of your program. The most common control structures in Python are if/else statements and loops.

Here is an example of an if/else statement:

```python
x = 5
if x > 10:
    print("x is greater than 10")
else:
    print("x is less than or equal to 10")
```

Here is an example of a loop:

```python
for i in range(0, 5):
    print(i)
```

### **Functions**

Functions are used to encapsulate a block of code that can be reused throughout your program. Here is an example of a Python function:

```python
def square(x):
    return x * x
```

In this example, we have defined a function called "square" that takes one argument, "x". The function returns the square of the argument.

### **File Input/Output**

Python provides built-in functions for reading from and writing to files. Here is an example of a Python program that reads from a file and prints the contents to the console:

```python
with open("file.txt", "r") as f:
    for line in f:
        print(line)
```

In this example, we have opened the file "file.txt" in read mode and printed each line to the console.

### **Conclusion**

In this lesson, we have covered the basics of Python programming language. You should now have a solid understanding of the Python syntax, variables and data types, control structures, functions, and file input/output. In the next lesson, we will explore more advanced Python topics.

## **Coding Challenge**

Write a Python program that takes a list of numbers as input and returns the sum of all the **even numbers** in the list.

Here's an example of what the program should do:

```python
Input: [1, 2, 3, 4, 5, 6]
Output: 12
```

In this example, the even numbers in the list are 2, 4, and 6, and their sum is 12.

To solve this challenge, you can use a loop to iterate over the list and an if statement to check if each number is even. If a number is even, add it to a running total of even numbers. At the end of the loop, return the total.

Here's some starter code to help you get started:

```python
def sum_even_numbers(numbers):
    total = 0
    for num in numbers:
        if num % 2 == 0:
            # add num to total
    return total
```

Your task is to complete the `sum_even_numbers` function by filling in the missing code. Good luck!

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy Coding!