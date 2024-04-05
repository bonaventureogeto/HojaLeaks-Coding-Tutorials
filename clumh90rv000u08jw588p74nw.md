---
title: "Understanding Javascript Runtime and Callbacks"
seoTitle: "Understanding Javascript Runtime and Callbacks"
datePublished: Fri Apr 05 2024 09:42:26 GMT+0000 (Coordinated Universal Time)
cuid: clumh90rv000u08jw588p74nw
slug: understanding-javascript-runtime-and-callbacks
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1711707852861/14180e61-dc94-437a-ab63-ee3441402359.jpeg
tags: software-development, programming-blogs, javascript, web-development, webdev, programming-languages

---

# Javascript Runtime

In Layman language, one would refer to Javascript runtime as the environment where JavaScript code is executed. According to us, JavaScript runtime is the engine that powers your code, making sure everything runs smoothly and your instructions are executed accurately and efficiently.

if a 10-year-old wanted to understand JavaScript runtime all we'd have to tell them is that it is a "helper" that brings your code to life. Without the Javascript Runtime, we wouldn't be able to execute any Javascript code.

To understand Java script Runtime you have to understand the following:

1. Execution environment - Javascript runtime provides the environment for executing javascript code
    
2. Event loop - it ensures that tasks are executed in the correct order and the application remains responsive
    
3. Call stack - this is a data structure that keeps track of function calls in the code
    
4. Heap - this is a region of memory where objects are stored
    
5. Concurrency model - JavaScript runtime uses a single-threaded concurrency model meaning only one task can be executed at a time...however it achieves asynchronous behaviour through mechanisms like callback, promises, and async/await allowing non-blocking input and output operations
    
6. Built-in objects and functions - the runtime provides built-in objects like array and string and functions like set timeout for common tasks
    
7. Error handling - JavaScript runtime handles runtime errors through mechanisms like try-catch blocks that prevent the program from crashing.
    

In other terms... imagine you have a big box of LEGO bricks, and you want to build something cool with them. JavaScript runtime is like the table where you build your LEGO creation. It's where your JavaScript code (which are like the instructions for building with LEGO) runs and does its job. So, just like how you need a table to build your LEGO masterpiece, JavaScript needs a runtime environment to do its work and make things happen on your computer or phone.

## Callbacks

A callback is a function passed as an argument to another function.

A call-back function. can run after another function has finished...this technique allows a function to call another function.

Callbacks in Javascript are like making promises to a friend. If you tell your friends that you will call them immediately after finishing how they can go and do other activities while waiting for your call and when you are finished with your homework they can come back to you and then you both can continue with what you were doing together.

Similarly, in JavaScript, you're basically saying "When you're done with this task call this function back"It allows JavaScript to run other code while waiting for something to finish. When the task is done, the callback function gets called, and JavaScript continues executing the rest of the code.

Callbacks are commonly used in asynchronous operations, like fetching data from a server, handling user input, or waiting for a file to load. They help JavaScript manage multiple tasks without getting stuck waiting for one task to finish before moving on to the next.

There are two ways in which callbacks can be called synchronous or asynchronous;

### Synchronous Callbacks

they are called and executed right away, blocking the execution of other code until they finish.

a deeper dive into synchronous callbacks there is:

* Immediate Execution
    
* Blocking Behavior
    
* Access to Execution
    
* return values
    

Let's visualize it with a simple analogy:

Imagine you are cooking in your kitchen. You have a recipe book (the higher-order function) with steps that need to be followed. Along with each step, there’s a note saying “Call my friend” (the synchronous callback) with instructions on what your friend needs to do next.

### 1\. Immediate Execution:

As you follow each step in the recipe book, whenever you encounter a note saying “call my friend,” you immediately pick up the phone and call your friend. You don’t wait for anything else; you call them right away.

### 2\. Blocking Behavior:

While you’re on the phone with your friend, you’re not able to continue cooking. You’re waiting for them to finish their task before you can proceed with the next step in the recipe. If your friend takes a long time to finish, you’re stuck waiting, and you can’t do anything else in the meantime.

### 3\. Access to Execution Context:

Since you’re in your kitchen, you and your friend have access to all the ingredients, utensils, and tools available in that space. You can both see and use everything that’s within reach.

### 4\. Return Values:

After your friend finishes their task (the synchronous callback), they might give you some information or feedback related to the task they performed. You can use this information to decide what to do next in your cooking process.

### 5\. Example:

Let’s say you’re making pancakes, and for each pancake, you need to flip it once it’s cooked on one side. You call your friend to flip the pancake when it’s ready. Your friend flips the pancake (the synchronous callback), and then you can continue with the next pancake without waiting for anything else.

In this analogy, the synchronous callback represents a task that needs to be performed immediately and synchronously within the flow of the main operation (cooking). While synchronous callbacks are straightforward to understand, they can cause the main operation to be blocked if the callback takes too long to execute.

![simple example to illustrate synchronous callbacks](https://cdn.hashnode.com/res/hashnode/image/upload/v1711711835721/5656bfb0-e66a-4f2c-ac57-69d94fdd2ef3.png align="center")

This is an example to illustrate synchronous callbacks

In this example:

1\. We have a higher-order function greet that takes a name parameter and a callback function callback.

2\. Inside greet, we perform the main operation, which is to log a greeting message to the console.

3\. After greeting the person, we immediately call the callback function callback.

4\. We define a synchronous callback function sayGoodbye that logs a farewell message to the console.

5\. Finally, we call the greet function with the name “Alice” and pass the sayGoodbye function as the callback.

When we run this code, it will output:

Hello, Alice! Goodbye!

Here, the synchronous callback sayGoodbye is executed immediately after the main operation (console.log("Hello, " + name + "!")) within the greet function. This demonstrates how synchronous callbacks are called and executed synchronously within the flow of the main operation.

### Asynchronous Callbacks

unlike synchronous callbacks asynchronous callbacks allow you to execute code without waiting for a task to finish.

when we take a deeper look into asynchronous callbacks we'll get to know about:

* Delayed Execution
    
* Non-Blocking Behavior
    
* Callback Invocation
    
* Event Loop
    

Let's delve into it using a practical analogy

Imagine you’re at a restaurant waiting for your food. You order your meal and receive a pager. The waiter tells you that when your food is ready, the pager will buzz, and you can come to collect your order. This pager system represents asynchronous callbacks in JavaScript.

Here’s a breakdown of asynchronous callbacks:

1. ### Delayed Execution:
    

Just like waiting for your food at the restaurant, asynchronous callbacks are not executed immediately. Instead, they are scheduled to run later, after the completion of a particular task or event.

3. ### Non-Blocking Behavior:
    

While you’re waiting for your food, you’re free to do other things, such as chatting with friends or browsing your phone. Similarly, in JavaScript, when an asynchronous operation is initiated (like fetching data from a server), the rest of the code can continue executing without waiting for the operation to finish.

3. ### Callback Invocation:
    

When the asynchronous task completes (your food is ready), the callback function is invoked or called back. This callback function then handles the result or response of the asynchronous operation.

4. ### Event Loops:
    

Imagine you’re at a busy restaurant with a single waiter. This waiter is responsible for taking orders, delivering food, and handling customer requests. However, there’s only one thing the waiter can do at a time.

Here’s how the restaurant’s operation represents the event loop:

### 1\. Taking Orders:

When customers arrive at the restaurant, they place their orders with the waiter. Similarly, when JavaScript code runs, it initiates tasks like fetching data from a server or handling user interactions.

### 2\. Delivering Food:

After taking an order, the waiter submits it to the kitchen. While the food is being prepared, the waiter doesn’t stand idle. Instead, they attend to other customers, take more orders, or handle requests from tables that need assistance. This mirrors how JavaScript continues executing other code while waiting for asynchronous tasks to complete.

### 3\. Customer Requests:

Sometimes, customers may have special requests or questions. The waiter addresses these requests promptly, ensuring all customers are satisfied. In JavaScript, events like mouse clicks or keyboard inputs trigger actions, and the event loop handles them as they occur.

### 4\. Busy Yet Responsive:

Despite being busy attending to multiple tasks, the waiter ensures the restaurant remains responsive. They don’t get overwhelmed by tasks piling up; instead, they efficiently manage their time and priorities. Similarly, the event loop in JavaScript ensures that tasks are executed in a timely manner, maintaining the responsiveness of web applications.

### 5\. Efficient Handling:

The waiter’s ability to juggle multiple tasks and handle requests as they come in represents the event loop’s efficiency in JavaScript. It ensures that tasks are executed in the correct order and that the application remains responsive to user interactions.

In essence, the event loop in JavaScript is like a diligent waiter at a busy restaurant, efficiently managing tasks and ensuring the smooth operation of the system despite the potentially overwhelming workload.

In essence, asynchronous callbacks allow you to write code that can handle multiple tasks concurrently, improving the responsiveness and efficiency of your JavaScript programs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1711713066991/405930f1-8232-4446-8bc7-510d2cf9a446.png align="center")

1\. The code starts by logging “Start” synchronously, meaning it executes immediately.

2\. Then, a call to setTimeout initiates an asynchronous operation. This operation schedules the provided callback function to be executed after a specified delay (in this case, 2000 milliseconds or 2 seconds). However, the rest of the code continues executing without waiting for the asynchronous operation to complete.

3\. Next, “End” is logged synchronously.

4\. After 2 seconds have passed, the callback function inside setTimeout is invoked asynchronously, and “Asynchronous operation complete” is logged to the console.

Output:

Start End Asynchronous operation complete

This example illustrates how asynchronous callbacks work in JavaScript. Despite being initiated asynchronously, the callback function is executed later, allowing other synchronous operations to continue without interruption.

### Callback Hell

Callback Hell (Callback Pyramids) in JavaScript, also known as the “Pyramid of Doom,” is a situation where **nested callbacks lead to deeply indented and hard-to-read code**. It can make your code look like a pyramid due to its visual structure.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1711713593120/b9a96bfd-1047-4961-8581-5c3a31b8c22f.png align="center")

• Each asyncOperation represents an asynchronous task.

• Each callback function is nested within the callback of the previous operation, leading to deeply nested code.

• This nesting makes the code difficult to read, understand, and maintain.

Callback hell can be avoided by using techniques like Promises or async/await, which provide cleaner and more readable alternatives for handling asynchronous operations.

### Promise

A promise in JavaScript is an object representing the eventual completion or failure of an asynchronous operation. It allows you to handle asynchronous tasks in a more organized and readable way by providing a cleaner syntax compared to traditional callback-based approaches.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1711713965345/961425b0-8af7-4573-96c1-788a002241f2.png align="center")

1\. The fetchData function returns a new Promise object. Inside the promise constructor, an asynchronous operation is simulated using setTimeout to mimic fetching data. If the operation is successful, the promise is resolved with the fetched data using the resolve function. If there’s an error, the promise is rejected with an error using the reject function.

2\. The promise returned by fetchData is consumed using the then method. This method registers a callback function to be executed when the promise is resolved. In this case, it logs the fetched data to the console.

3\. The catch method is used to handle any errors that occur during the promise chain. If the promise is rejected (e.g., if there’s an error fetching data), the error is caught and logged to the console.

This example demonstrates how promises can be used to handle asynchronous operations and manage their eventual completion or failure in a structured and readable way.

### Async/Await

Async/await is a modern JavaScript feature that simplifies asynchronous code and makes it look and behave more like synchronous code. It’s built on top of Promises and provides a cleaner and more concise syntax for handling asynchronous operations.