---
title: "Free Tutorial: 5 JavaScript Data Types Explained"
seoTitle: "Tutorial: JavaScript Data Types"
datePublished: Mon Jan 16 2023 17:29:54 GMT+0000 (Coordinated Universal Time)
cuid: clcz303xd000608jn5zj3ed0p
slug: free-tutorial-5-javascript-data-types-explained
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1673889666726/4e29570a-bb6f-4e23-9065-c8d594ab99a9.jpeg
tags: tutorial, programming-blogs, javascript, web-development, webdev

---

JavaScript is a dynamic and loosely typed language, which means that it automatically determines the data type of a variable based on the value assigned to it.

### Number

The number data type is used to represent numbers in JavaScript. It can be either an integer or a floating-point number. Examples of numbers include:

* 1
    
* 3.14
    
* \-5
    
* Infinity
    
* NaN (Not a Number)
    

You can perform mathematical operations on numbers such as addition, subtraction, multiplication, and division.

```javascript
let num1 = 10;
let num2 = 5;

console.log(num1 + num2); // 15
console.log(num1 - num2); // 5
console.log(num1 * num2); // 50
console.log(num1 / num2); // 2
```

Coding Challenge:

Write a JavaScript program that calculates the area of a circle given the radius. The formula for the area of a circle is A = πr².

```javascript
let radius = 5;
let area = Math.PI * Math.pow(radius, 2);
console.log(area); // 78.53981633974483
```

### String

The string data type is used to represent a sequence of characters. Strings are enclosed in single or double quotes. Examples of strings include:

* "Hello World"
    
* 'JavaScript'
    
* "123"
    

You can manipulate strings using various methods such as concatenation, substring, and replace.

```javascript
let firstName = "John";
let lastName = "Doe";

console.log(firstName + " " + lastName); // John Doe
console.log(firstName.substring(0, 2)); // Jo
console.log(lastName.replace("Doe", "Smith")); // Smith
```

Coding Challenge:

Write a JavaScript program that takes a string and returns the number of vowels in the string.

```javascript
let str = "JavaScript";
let vowels = "aeiouAEIOU";
let count = 0;

for (let i = 0; i < str.length; i++) {
  if (vowels.indexOf(str[i]) !== -1) {
    count++;
  }
}
console.log(count); // 3
```

### Boolean

The boolean data type is used to represent true or false values. Examples of booleans include:

* true
    
* false
    

Booleans are often used in conditional statements such as if-else or while loops to determine the flow of a program.

```javascript
let isTrue = true;
let isFalse = false;

if (isTrue) {
  console.log("This is true");
} else {
  console.log("This is false");
}
```

Coding Challenge:

Write a JavaScript program that takes in a number and returns true if the number is even and false if the number is odd.

```javascript
let num = 7;

if (num % 2 === 0) {
  console.log(true);
} else {
  console.log(false);
}
```

### **Array**

The array data type is used to store a collection of values. Arrays are enclosed in square brackets and values are separated by commas.

1. Examples of arrays include:
    
    * \[1, 2, 3, 4\]
        
    * \["JavaScript", "CSS", "HTML"\]
        
    * \[true, false, true\]
        
    
    You can access and manipulate elements in an array using methods such as push, pop, and slice.
    

```javascript
let myArray = [1, 2, 3, 4];

console.log(myArray[0]); // 1
myArray.push(5); // [1, 2, 3, 4, 5]
console.log(myArray.pop()); // 5
console.log(myArray.slice(1, 3)); // [2, 3]
```

Coding Challenge:

Write a JavaScript program that takes in an array of numbers and returns the average of all the numbers in the array.

```javascript
let numArray = [1, 2, 3, 4, 5];
let sum = 0;

for (let i = 0; i < numArray.length; i++) {
  sum += numArray[i];
}
console.log(sum / numArray.length); // 3
```

### Object

The object data type is used to store key-value pairs. Objects are enclosed in curly braces {} and properties are represented by key-value pairs separated by a colon. Examples of objects include:

* {name: "John", age: 30}
    
* {color: "red", size: "large"}
    

You can access and manipulate properties in an object using dot notation or bracket notation.

```javascript
let myObject = {name: "John", age: 30};

console.log(myObject.name); // John
myObject.age = 35;
console.log(myObject["age"]); // 35
```

Coding Challenge:

Write a JavaScript program that takes in an object representing a person and returns a string of their full name.

```javascript
let person = {firstName: "John", lastName: "Doe"};

console.log(person.firstName + " " + person.lastName); // John Doe
```

In conclusion, understanding the different data types in JavaScript is crucial for writing efficient and effective code. Practice working with these data types through coding challenges and experimenting with different methods and operations to solidify your understanding.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!