---
title: "JavaScript 101: Understanding Promises, Async & Await"
seoTitle: "JavaScript 101: Promises, Async & Await Explained"
datePublished: Mon Feb 06 2023 05:43:58 GMT+0000 (Coordinated Universal Time)
cuid: cldse15w0000009l05lavc8km
slug: javascript-101-understanding-promises-async-await
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1675662129929/ed6860a4-8b28-4c11-8505-58c2adc23625.png
tags: programming-blogs, javascript, web-development, webdev, wemakedevs

---

Promises, Async & Await are all related concepts in JavaScript that are used to handle asynchronous operations.

A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation, and its resulting value. Promises provide a way to register callbacks to be called when the async operation completes or fails.

Promises have three states:

* Pending: The initial state, neither fulfilled nor rejected.
    
* Fulfilled: This means that the operation was completed successfully.
    
* Rejected: This means that the operation failed.
    

Here is an example of a basic promise:

```javascript
const myPromise = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Hello from myPromise!");
    }, 1000);
});

myPromise.then(console.log);
```

This promise will log "Hello from myPromise!" after one second.

Async & Await are JavaScript keywords that are used to handle promises. The `async` keyword defines an asynchronous function, which returns a promise. The `await` keyword is used to wait for a promise to be resolved before moving on to the next line of code.

Here is an example of an asynchronous function using `async` & `await`:

```javascript
async function myAsyncFunction() {
    const myPromise = new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve("Hello from myAsyncFunction!");
        }, 1000);
    });
    const result = await myPromise;
    console.log(result);
}

myAsyncFunction();
```

This function will log "Hello from myAsyncFunction!" after one second.

Note: The `await` keyword can only be used within an `async` function.

In summary, Promises provide a way to handle async operations, and Async & Await provides a more straightforward way to handle promises, allowing you to write async code that looks and behaves like sync code.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!