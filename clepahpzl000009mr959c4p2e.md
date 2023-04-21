---
title: "JavaScript Concepts: Object-Oriented Programming, Inheritance, Classes, Error Handling, Asynchronous Programming, Generators, and More"
seoTitle: "Understanding JavaScript Concepts: OOP and More"
datePublished: Wed Mar 01 2023 06:21:16 GMT+0000 (Coordinated Universal Time)
cuid: clepahpzl000009mr959c4p2e
slug: javascript-concepts-object-oriented-programming-inheritance-classes-error-handling-asynchronous-programming-generators-and-more
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1677651485457/bd695427-aa75-4eeb-b9d3-8ed77ea289c4.jpeg
tags: software-development, programming-blogs, javascript, web-development, webdev

---

### **Prototypes**

In JavaScript, prototypes are used to share properties and methods among objects. Every object in JavaScript has a prototype, which is an object that it can inherit properties and methods from.

For example, let's say we have a `Car` constructor function:

```javascript
function Car(make, model) {
  this.make = make;
  this.model = model;
}
```

When we create a new object with this constructor function, it will have a prototype with the default object methods such as `toString()`, `valueOf()` etc. But we can also add our own methods to the prototype:

```javascript
Car.prototype.start = function() {
  console.log("The car is starting");
};
```

Now, every object created with the `Car` constructor function will have access to the `start` method. This is useful for adding methods that should be shared among all instances of an object, rather than having to add them to each individual object.

Additionally, we can also add properties to the prototype:

```javascript
Car.prototype.wheels = 4;
```

This way, all instances of the object will have access to the property.

### **Inheritance**

JavaScript uses prototype-based inheritance, which allows objects to inherit properties and methods from their prototypes. We can create a new object that inherits from another object's prototype by using the `Object.create()` method.

For example, let's say we have a `ElectricCar` constructor function that inherits from the `Car` constructor function:

```javascript
function ElectricCar(make, model) {
  Car.call(this, make, model);
}

ElectricCar.prototype = Object.create(Car.prototype);
ElectricCar.prototype.constructor = ElectricCar;
```

Now, all instances of the `ElectricCar` object will have access to the properties and methods on the `Car` prototype, as well as any properties and methods on its own prototype.

### **Classes**

ECMAScript 6 introduced the `class` keyword, which provides a more familiar syntax for creating objects and implementing inheritance in JavaScript. A class is a blueprint for an object, and an object is an instance of a class.

For example, let's convert the `Car` constructor function from earlier into a class:

```javascript
class Car {
  constructor(make, model) {
    this.make = make;
    this.model = model;
  }

  start() {
    console.log("The car is starting");
  }
}
```

We can create an object with the `Car` class using the `new` keyword, just like with a constructor function:

```javascript
let myCar = new Car("Toyota", "Camry");
```

And we can also create a class that inherits from another class using the `extends` keyword:

```javascript
class ElectricCar extends Car {
  constructor(make, model) {
    super(make, model);
  }
}
```

### **Error Handling**

Error handling is the process of dealing with errors that occur during the execution of a program. JavaScript provides the `try` and `catch` statements for handling errors. The `try` block contains the code that might throw an error, and the `catch` block contains the code that will handle the error.

For example, let's say we have a function that might throw an error:

```javascript
function divide(a, b) {
  if (b === 0) {
    throw new Error("Cannot divide by zero");
  }
  return a / b;
}
```

We can use a `try` and `catch` block to handle the error:

```javascript
try {
  let result = divide(10, 0);
  console.log(result);
} catch (error) {
  console.log(error.message); // Cannot divide by zero
}
```

In this example, if the error is thrown, the program will jump to the catch block and execute the code inside it, in this case, it will print the error message.

It's also possible to use a `finally` block, which will execute code regardless of whether an error is thrown or not.

### **Promises, Async & Await**

JavaScript provides a way to handle asynchronous code through the use of promises, async functions, and the await keyword.

A promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. Promises have a `then` method, which allows us to register callbacks to be called when the promise is fulfilled (resolved), and a `catch` method, which allows us to register callbacks to be called when the promise is rejected.

For example:

```javascript
let promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Hello World");
  }, 1000);
});

promise.then(result => {
  console.log(result); // Hello World
}).catch(error => {
  console.log(error);
});
```

Async functions are a way to write asynchronous code that looks and behaves like synchronous code. Async functions return a promise, and we can use the `await` keyword inside an async function to wait for a promise to resolve.

For example:

```javascript
async function getData() {
  let result = await fetch("https://api.example.com");
  let json = await result.json();
  console.log(json);
}
```

In this example, the `await` keyword is used to wait for the fetch request to complete and the json method to complete, before moving on to the next line.

### **Generators**

Generators are a special type of function in JavaScript that allows us to generate a sequence of values over time. They are defined using the `function*` syntax, and we can use the `yield` keyword to return a value from the generator.

For example:

```javascript
function* count() {
  for (let i = 1; i <= 10; i++) {
    yield i;
  }
}

let counter = count();
console.log(counter.next().value); // 1
console.log(counter.next().value); // 2
console.log(counter.next().value); // 3
```

In this example, we are using the `next` method to move to the next value in the generator, and the `value` property to access the current value.

### **Miscellaneous**

There are many other concepts and features in JavaScript that are important to understand and master, such as the event loop, hoisting, closures, and the module system.

Event loop is the mechanism that JavaScript uses to handle asynchronous code execution. It allows the execution of code to be delayed until other code has completed execution.

Hoisting is the behavior in which variable and function declarations are moved to the top of their scope. This means that variable and function declarations are accessible before they are actually defined in the code.

Closures are a powerful feature of JavaScript that allows for data privacy and encapsulation. A closure is a function that has access to variables in its parent scope even after the parent function has returned.

Modules are a way to organize and reuse code in JavaScript. ECMAScript 6 introduced the `import` and `export` keywords for creating and using modules. Modules help to keep the global scope clean and make the code more maintainable.

Understanding these concepts and features will help you to write more efficient and effective code in JavaScript. It's important to practice and continue learning about these and other concepts in JavaScript to become a proficient JavaScript developer.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy coding!