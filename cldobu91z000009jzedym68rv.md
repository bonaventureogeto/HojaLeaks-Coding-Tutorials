---
title: "Tutorial: Test-Driven Development in Python"
seoTitle: "Tutorial: Test-Driven Development in Python"
datePublished: Fri Feb 03 2023 09:31:31 GMT+0000 (Coordinated Universal Time)
cuid: cldobu91z000009jzedym68rv
slug: tutorial-test-driven-development-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1675416627157/0d883fae-7842-4ab7-b829-b159077b4201.png
tags: tdd, programming-blogs, python, python3, python-beginner

---

Test-driven development (TDD) is a software development process where developers write tests before writing the actual code. The tests check the functionality of the code, and the code is written to make the tests pass. TDD helps ensure that the code is reliable, maintainable, and can be refactored without breaking. In this tutorial, we'll cover TDD in Python and demonstrate the process with examples.

## **Setting up the Environment**

To get started, you need to install the following:

1. Python 3
    
2. The unittest module that comes with Python
    

You can check if you have Python installed by running the following command in your terminal or command prompt:

```bash
python --version
```

## **Writing Tests**

The first step in TDD is to write tests that check the functionality of your code. You'll use the unittest module to write these tests.

Here's an example of how to write a test for a function that calculates the factorial of a number:

```python
import unittest

def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)

class TestFactorial(unittest.TestCase):
    def test_factorial(self):
        self.assertEqual(factorial(0), 1)
        self.assertEqual(factorial(1), 1)
        self.assertEqual(factorial(2), 2)
        self.assertEqual(factorial(3), 6)
        self.assertEqual(factorial(4), 24)
```

In this example, we define a function called `factorial` that calculates the factorial of a number. Then, we create a test case class called `TestFactorial` that inherits from `unittest.TestCase`. Inside the class, we define a test method called `test_factorial` that checks the output of the `factorial` function for different input values.

The `assertEqual` method is used to check if the output of the `factorial` function is equal to the expected value. If the output is not equal to the expected value, the test will fail and an error message will be displayed.

## **Running Tests**

To run the tests, you can use the following command:

```bash
python -m unittest <test_file_name>
```

In the example above, the test file name is `test_factorial.py`. So, to run the tests, you would use the following command:

```bash
python -m unittest test_factorial
```

If all the tests pass, you'll see an output similar to the following:

```markdown
....
----------------------------------------------------------------------
Ran 4 tests in 0.000s

OK
```

If any of the tests fail, you'll see an output similar to the following:

```markdown
..F
======================================================================
FAIL: test_factorial (__main__.TestFactorial)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "test_factorial.py", line 14, in test_factorial
    self.assertEqual(factorial(2), 1)
AssertionError: 2 != 1

----------------------------------------------------------------------
Ran 4 tests in 0.000s

FAILED (failures=1)
```

## **Writing Code**

Once you've written the tests, the next step is to write the code that makes the tests pass. The goal is to write the minimum amount of code necessary to make the tests pass.

Here's an example of how to write the code for the factorial function:

```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)
```

In this example, the `factorial` function uses recursion to calculate the factorial of a number. If the input is 0, the function returns 1. If the input is not 0, the function returns `n * factorial(n-1)`, where `n` is the input.

## **Re-running Tests**

After writing the code, re-run the tests to see if they pass. If all the tests pass, you're done! If any of the tests fail, fix the code and re-run the tests until all the tests pass.

Here's an example of what the output might look like after running the tests:

```markdown
.....
----------------------------------------------------------------------
Ran 4 tests in 0.000s

OK
```

## **Refactoring**

Once the tests pass, you can refactor the code to make it more readable, efficient, or maintainable. However, before refactoring the code, re-run the tests to make sure they still pass. If any of the tests fail, fix the code and re-run the tests until all the tests pass.

In the example above, the `factorial` function is simple and efficient, so there's no need to refactor it.

## **Conclusion**

We've covered the basics of TDD in Python. We've shown how to write tests, run tests, write code, and refactor code using the unittest module. By following the TDD process, you can write reliable, maintainable, and testable code.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!