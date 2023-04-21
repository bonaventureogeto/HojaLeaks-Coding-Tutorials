---
title: "JavaScript 101: An Introduction to the Basics and Fundamentals of the Language"
seoTitle: "JavaScript 101: An Introduction to the Basics and Fundamentals"
datePublished: Mon Dec 19 2022 11:23:07 GMT+0000 (Coordinated Universal Time)
cuid: clbupkklw000408l0fhvt8xhc
slug: javascript-101
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1671448248024/iHg229XRh.jpg
tags: programming-blogs, javascript, web-development, reactjs, beginners

---

Welcome to this tutorial on the basics of JavaScript! JavaScript is a popular programming language that is used to create interactive elements on websites, such as drop-down menus, form validation, and interactive maps. It is also a powerful language that can be used to build full-fledged web applications.

In this tutorial, we will cover the following topics:

1. What is JavaScript and where is it used?
    
2. Setting up a development environment for JavaScript
    
3. Basic syntax and data types in JavaScript
    
4. Variables in JavaScript
    
5. Operators in JavaScript
    
6. Control structures in JavaScript (if/else statements, loops)
    
7. Functions in JavaScript
    
8. Objects in JavaScript
    

Let's get started!

## **1\. What is JavaScript and where is it used?**

JavaScript is a programming language that is primarily used to create interactive elements on websites. It is a client-side language, which means that the code is executed on the user's computer, rather than on the server.

JavaScript is used to make websites more dynamic and interactive. For example, you can use JavaScript to validate form input, create drop-down menus, and display pop-up windows. It is also used to create games, mobile apps, and desktop applications.

## **2\. Setting up a development environment for JavaScript**

Before you start coding with JavaScript, you need to set up a development environment. This involves installing a text editor to write your code and a web browser to run and test your code.

Some popular text editors for writing JavaScript code include Sublime Text, Atom, and Visual Studio Code. Any of these text editors will work fine for this tutorial.

You will also need a web browser to test your code. Most modern web browsers, such as Google Chrome, Mozilla Firefox, and Microsoft Edge, have built-in JavaScript engines that can execute JavaScript code.

## **3\. Basic syntax and data types in JavaScript**

JavaScript has a similar syntax to C-style languages such as C++ and Java. It uses curly braces to define blocks of code, and semicolons to separate statements.

Here is a simple example of a JavaScript program that displays "Hello, World!" in the web browser:

```javascript
// This is a single-line comment

/*
This is a multi-line comment
*/

console.log("Hello, World!"); // Outputs "Hello, World!" to the console
```

In JavaScript, there are several data types that can be used to store data:

* **Number**: Numbers can be integers (e.g. 1, 2, 3) or floating-point values (e.g. 3.14, 4.5). In JavaScript, there is only one type of number, and it can represent both integers and floating-point values.
    
* **String**: Strings are used to store character data, and are written using single or double quotes. For example: 'Hello, World!' or "Hello, World!".
    
* **Boolean**: Booleans can only have two values: true or false. They are often used to represent the truth value of a statement.
    
* **null**: The null value represents an absence of value or a null reference.
    
* **undefined**: The undefined value represents a value that has not been defined or assigned.
    

## **4\. Variables in JavaScript**

In JavaScript, variables are used to store data. They are named storage locations that can contain different types of data.

To declare a variable in JavaScript, use the `var` keyword followed by the name of the variable. For example:

```javascript
var x; // Declares a variable named x
```

You can also assign a value to a variable when you declare it. For example:

```javascript
var x = 5; // Declares a variable named x and assigns it the value of 5
```

JavaScript is a loosely typed language, meaning you don't have to specify the variable's data type when you declare it. The data type of the variable will be determined based on the value that is assigned to it.

For example:

```javascript
var x = 5; // x is a number
var y = "hello"; // y is a string
```

You can also use the `let` and `const` keywords to declare variables in JavaScript. The `let` keyword is used to declare variables that can be reassigned, while the `const` keyword is used to declare variables that cannot be reassigned.

For example:

```javascript
let x = 5; // x is a variable that can be reassigned
console.log(x); // 5
x = 6; // x is now 6

const y = "hello"; // y is a constant that cannot be reassigned
y = "world"; // This will throw an error
```

## **5\. Operators in JavaScript**

JavaScript has a variety of operators that can be used to perform different types of operations.

### **Arithmetic operators**

JavaScript has the usual arithmetic operators that you would expect, such as `+`, `-`, `*`, and `/`. For example:

```javascript
var x = 5 + 2; // x is 7
var y = x * 3; // y is 21
var z = y / 4; // z is 5.25
var k = y % x; // modulus is 0
```

### **Comparison operators**

JavaScript has comparison operators that can be used to compare values and return a boolean value of true or false. These include `==` (equal to), `!=` (not equal to), `>` (greater than), `<` (less than), `>=` (greater than or equal to), and `<=` (less than or equal to).

For example:

```javascript
var x = 5;
var y = 2;

console.log(x == y); // false
console.log(x != y); // true
console.log(x > y); // true
console.log(x < y); // false
console.log(x >= y); // true
console.log(x <= y); // false
```

### **Logical operators**

JavaScript has logical operators that can be used to combine boolean values. These include `&&` (and), `||` (or), and `!` (not).

For example:

```javascript
var x = true;
var y = false;

console.log(x && y); // false
console.log(x || y); // true
console.log(!x); // false
```

## **6\. Control structures in JavaScript**

Control structures are used to control the flow of execution in a program. JavaScript has several control structures that can be used to perform different actions based on different conditions.

### **if/else statements**

An if/else statement is used to execute a block of code if a certain condition is true, or a different block of code if the condition is false.

Here is an example of an if/else statement:

```javascript
var x = 5;

if (x > 10) {
  console.log("x is greater than 10");
} else {
  console.log("x is not greater than 10");
}
```

In this example, the code in the first block (`console.log("x is greater than 10")`) will only be executed if the condition (`x > 10`) is true. If the condition is false, the code in the second block (`console.log("x is not greater than 10")`) will be executed instead.

You can also use an `else if` statement to add additional conditions to be checked. For example:

```javascript
var x = 5;

if (x > 10) {
  console.log("x is greater than 10");
} else if (x < 0) {
  console.log("x is less than 0");
} else {
  console.log("x is between 0 and 10");
}
```

### **Loops**

Loops are used to execute a block of code multiple times. JavaScript has two types of loops: `for` loops and `while` loops.

A `for` loop is used to repeat a block of code a specific number of times. The syntax for a `for` loop is:

```javascript
for (initialization; condition; increment) {
  // code to be executed
}
```

Here is an example of a `for` loop that prints the numbers 1 to 5 to the console:

```javascript
for (var i = 1; i <= 5; i++) {
  console.log(i);
}
```

A `while` loop is used to repeat a block of code while a certain condition is true. The syntax for a `while` loop is:

```javascript
while (condition) {
  // code to be executed
}
```

Here is an example of a `while` loop that prints the numbers 1 to 5 to the console:

```javascript
var i = 1;
while (i <= 5) {
  console.log(i);
  i++;
}
```

## **7\. Functions in JavaScript**

Functions are blocks of code that can be defined and then called by name. They are used to perform a specific task and can accept input (called parameters) and return output (called a return value).

To define a function in JavaScript, use the `function` keyword followed by the name of the function and a set of parentheses. The code to be executed by the function is written inside curly braces.

For example:

```javascript
function greet() {
  console.log("Hello, World!");
}
```

To call a function, simply use its name followed by a set of parentheses. For example:

```javascript
greet(); // Outputs "Hello, World!" to the console
```

You can also pass parameters to a function by including them within the parentheses when calling the function. The values of the parameters are then passed to the function as arguments.

For example:

```javascript
function greet(name) {
  console.log("Hello, " + name + "!");
}

greet("John"); // Outputs "Hello, John!" to the console
greet("Jane"); // Outputs "Hello, Jane!" to the console
```

To return a value from a function, you can use the `return` keyword followed by the value to be returned. For example:

```javascript
function add(x, y) {
  return x + y;
}

console.log(add(2, 3)); // Outputs 5 to the console
```

You can also use the return value of a function in other operations or assignments. For example:

```javascript
function add(x, y) {
  return x + y;
}

var result = add(2, 3) * 2; // result is 10
```

## **8\. Objects in JavaScript**

Objects are used to store collections of data and functions that operate on that data. They are a fundamental part of the object-oriented programming paradigm in JavaScript.

An object is created using the `{}` syntax. You can define properties (data) and methods (functions) within an object using key-value pairs.

For example:

```javascript
var person = {
  name: "John",
  age: 30,
  greet: function() {
    console.log("Hello, my name is " + this.name);
  }
};
```

In this example, the `person` object has three properties: `name`, `age`, and `greet`. The `greet` property is a function that outputs a greeting to the console.

You can access the properties and methods of an object using the `.` operator. For example:

```javascript
console.log(person.name); // Outputs "John" to the console
person.greet(); // Outputs "Hello, my name is John" to the console
```

You can also add, modify, and delete properties and methods of an object using the `.` operator. For example:

```javascript
person.country = "United States"; // Adds a new property to the object
person.age = 31; // Modifies the age property
delete person.greet; // Deletes the greet method
```

That concludes our tutorial on the basics of JavaScript! I hope you have a better understanding of the fundamentals of this powerful programming language.

I'd love to connect with you via [Twitter](https://twitter.com/bonaogeto) | [LinkedIn](https://www.linkedin.com/in/bonaventureogeto/)

### **To support this free course and more to come,** [***buy me a coffee***](https://www.buymeacoffee.com/bonaogeto)