---
title: "Python Modules, Packages, and Conventions"
seoTitle: "Python Modules, Packages, and Conventions"
datePublished: Mon Mar 06 2023 15:27:22 GMT+0000 (Coordinated Universal Time)
cuid: clewz79sq000209lb4hm3hydq
slug: python-modules-packages-and-conventions
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/vb-3qEe3rg8/upload/d71e4ab0a39e07c0c6071fc316421cb7.jpeg
tags: software-development, programming-blogs, python, python3, python-beginner

---

Python is a powerful and flexible programming language that has been widely adopted in many industries. One of the reasons for its popularity is its rich ecosystem of modules and packages. In this tutorial, we'll discuss how to use modules and packages in Python, as well as some best practices and conventions to follow when working with them.

## Modules

A module is a file containing Python definitions and statements. The file name is the module name with the suffix `.py`. For example, if we have a file named [`hello.py`](http://hello.py) with the following contents:

```python
def say_hello(name):
    print(f"Hello, {name}!")
```

We can import it into another file using the `import` statement:

```python
import hello

hello.say_hello("World")
```

This will output `Hello, World!` to the console.

We can also import specific functions or variables from a module using the `from ... import` statement:

```python
from hello import say_hello

say_hello("Python")
```

This will output `Hello, Python!` to the console.

## Packages

A package is a way of organizing related modules together. A package is simply a directory containing a special file called `__init__.py`. The `__init__.py` file can be empty, or it can contain Python code that is executed when the package is imported.

Let's say we have a directory structure like this:

```python
my_package/
    __init__.py
    module1.py
    module2.py
```

We can import the modules like this:

```python
import my_package.module1
import my_package.module2

my_package.module1.function1()
my_package.module2.function2()
```

Or we can use the `from ... import ...` statement to import specific functions or variables:

```python
from my_package.module1 import function1
from my_package.module2 import variable2

function1()
print(variable2)
```

This will execute `function1()` from [`module1.py`](http://module1.py) and print the value of `variable2` from [`module2.py`](http://module2.py).

## Conventions

When working with modules and packages, it's important to follow some conventions to make your code more readable and maintainable. Here are some best practices to follow:

* Use descriptive names for modules and packages. This will make it easier for other developers to understand what your code does.
    
* Use lower\_case\_with\_underscores for module and package names. This is the recommended naming convention in Python.
    
* Use relative imports within a package. For example, if you have a module named [`module1.py`](http://module1.py) and another module named [`module2.py`](http://module2.py) in the same package, you should use the following import statement in [`module2.py`](http://module2.py):
    
    ```python
    from . import module1
    ```
    
    This tells Python to look for [`module1.py`](http://module1.py) in the same package as [`module2.py`](http://module2.py).
    
* Avoid using `*` in `from ... import ...` statements. This can make it difficult to understand which functions or variables are being imported, and it can also lead to naming conflicts.
    
* Use `if __name__ == "__main__":` to define a block of code that should only be executed if the module is run as the main program. This is a common convention in Python, and it allows you to write code that can be both imported as a module and run as a standalone program.
    

## Conclusion

Python modules and packages are powerful tools for organizing and reusing code. By following some simple conventions, you can make your code more readable, maintainable, and reusable.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy Coding!