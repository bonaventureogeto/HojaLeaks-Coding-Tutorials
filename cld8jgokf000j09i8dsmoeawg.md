---
title: "Object-Oriented Programming(OOP) in JavaScript 101: A Complete Guide"
seoTitle: "Object-Oriented Programming(OOP) in JavaScript 101: A Complete Guide"
datePublished: Mon Jan 23 2023 08:20:36 GMT+0000 (Coordinated Universal Time)
cuid: cld8jgokf000j09i8dsmoeawg
slug: object-oriented-programming-in-javascript-101-a-complete-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1674461460982/c34cc669-e184-4e13-9e86-f1f3ba91ed7c.png
tags: programming-blogs, javascript, web-development, programming-languages, object-oriented-programming

---

Object-Oriented Programming (OOP) is a programming paradigm that uses objects and their interactions to design applications and computer programs. JavaScript, being a multi-paradigm programming language, supports OOP through its constructor function and prototype-based inheritance.

### **Constructor function**

A constructor function is a special type of function that is used to create and initialize an object. The constructor function is called with the `new` keyword to create a new object.

```javascript
function Car(make, model) {
  this.make = make;
  this.model = model;
  this.year = new Date().getFullYear();
}

let myCar = new Car("Toyota", "Camry");
console.log(myCar); // { make: "Toyota", model: "Camry", year: 2020 }
```

In the example above, we have created a constructor function called `Car`, which takes in two parameters `make` and `model`. The `this` keyword is used to create properties on the object that is being constructed. In this case, `make`, `model` and `year` are properties of the object.

When we use the `new` keyword to create a new object, JavaScript creates a new object and sets the `this` keyword inside the constructor function to point to this new object. Then the constructor function is called, creating the properties `make`, `model` and `year` on the new object.

### **Prototype**

A prototype is an object that is shared among all instances of a constructor function. It is used to add properties and methods to all objects created by a constructor function.

```javascript
Car.prototype.start = function() {
  console.log("The car is starting");
};

myCar.start(); // The car is starting
```

In the example above, we have added a method called `start` to the prototype of the `Car` constructor function. This means that all objects created by the `Car` constructor function will have access to this method.

Notice that we are adding the `start` method to the prototype of the constructor function, not to the object instance. This is because the prototype is shared among all instances, so if we add a property or method to the prototype, it will be accessible on all instances of the constructor function.

### **Inheritance**

JavaScript uses prototype-based inheritance, which means that an object can inherit properties and methods from its prototype.

```javascript
function ElectricCar(make, model) {
  Car.call(this, make, model);
}

ElectricCar.prototype = Object.create(Car.prototype);
ElectricCar.prototype.constructor = ElectricCar;

let myElectricCar = new ElectricCar("Tesla", "Model S");
console.log(myElectricCar); // { make: "Tesla", model: "Model S", year: 2020 }
console.log(myElectricCar instanceof ElectricCar); // true
console.log(myElectricCar instanceof Car); // true
```

In the example above, we have created a new constructor function called `ElectricCar` which inherits from the `Car` constructor function. We accomplish this by using the `Object.create()` method to create a new object with the `Car.prototype` as its prototype. Then we set the `prototype` of the `ElectricCar` constructor function to this new object.

Additionally, we need to set the `constructor` property of the `ElectricCar` prototype to the `ElectricCar` constructor function, because the `Object.create()` method creates an object without a constructor property.

Now when we create a new instance of the `ElectricCar` constructor function, it inherits all properties and methods from the `Car` prototype, including the `start` method we added earlier.

In addition to this, we can check the type of the object using the `instanceof` operator. This will check if the object is an instance of the given constructor function, and in this case, it will return `true` for both `ElectricCar` and `Car`.

### **Encapsulation**

Encapsulation is the technique of hiding the internal state and behavior of an object and exposing a public interface. In JavaScript, this can be achieved by using closures and the `this` keyword.

```javascript
function BankAccount(balance) {
  let _balance = balance;

  this.getBalance = function() {
    return _balance;
  };

  this.deposit = function(amount) {
    _balance += amount;
  };

  this.withdraw = function(amount) {
    if (_balance >= amount) {
      _balance -= amount;
    } else {
      console.log("Insufficient funds");
    }
  };
}

let account = new BankAccount(1000);
console.log(account.getBalance()); // 1000
account.deposit(500);
console.log(account.getBalance()); // 1500
account.withdraw(2000); // Insufficient funds
```

In this example, we have created a `BankAccount` constructor function, which takes in an initial balance as a parameter. We are using closure to keep the `_balance` variable private and not accessible from the outside.

Notice that we are returning functions as the ***getter and setter methods***, this way they will have access to the private variable. This allows the developer to control how the internal state of the object is accessed and modified, which helps to maintain the integrity of the object's state.

In this way, we have created a public interface for the `BankAccount` object, which allows the user to check the balance, deposit money and withdraw money, but the internal state of the object is hidden from the user.

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

### Conclusion

This is a basic tutorial for OOP in JavaScript, but it's important to continue practicing and learning about OOP since javascript has a lot of nuances and ways to implement OOP, and also to explore other concepts related to javascript like scope, closures, and more.

Also, you should note that this is one way of implementing OOP in javascript, there are other methods like using classes and the `class` keyword, which was introduced in ECMAScript 6, this provides a cleaner and more familiar syntax for class-based OOP.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!