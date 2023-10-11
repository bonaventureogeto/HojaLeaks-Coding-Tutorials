---
title: "Introduction to Node.js"
seoTitle: "Introduction to Node.js 101"
datePublished: Wed Oct 11 2023 09:36:26 GMT+0000 (Coordinated Universal Time)
cuid: clnlk3iuq000i09mngms925tq
slug: introduction-to-nodejs
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/4hbJ-eymZ1o/upload/a7be3428dcc11e0f5fc61df753a0d468.jpeg
tags: javascript, web-development, nodejs, backend, webdev

---

Node.js is a popular runtime environment that allows you to write server-side JavaScript applications. It's built on the V8 JavaScript engine, the same engine that powers Google Chrome, and provides an event-driven, non-blocking I/O model that makes it well-suited for building scalable, high-performance applications.

Node.js is also popular because it has a huge ecosystem of packages and modules available through the Node Package Manager (npm), which makes it easy to incorporate third-party code into your applications.

## **Setting up Node.js**

Before you can start building Node.js applications, you need to install Node.js on your computer. You can download the installer from the official Node.js website ([**https://nodejs.org/en/download/**](https://nodejs.org/en/download/)) and follow the instructions to install it on your system.

Once you've installed Node.js, you can verify that it's installed correctly by running the following command in your terminal or command prompt:

```bash
node -v
```

This should print the version number of Node.js that you just installed.

## **Creating a Simple Node.js Application**

To create a simple Node.js application, you'll need to follow these steps:

1. Create a new directory for your project.
    
2. Navigate to that directory in your terminal or command prompt.
    
3. Initialize a new Node.js project by running the following command:
    
    ```bash
    npm init
    ```
    
    This will prompt you to enter some information about your project, such as its name, version, and description. You can accept the default values for most of these prompts by pressing enter, but you can also customize them if you like.
    
4. Create a new file called `index.js` in your project directory. This will be the entry point for your application.
    
5. Open `index.js` in your code editor and add the following code:
    
    ```javascript
    const http = require('http');
    
    const hostname = '127.0.0.1';
    const port = 3000;
    
    const server = http.createServer((req, res) => {
      res.statusCode = 200;
      res.setHeader('Content-Type', 'text/plain');
      res.end('Hello, world!');
    });
    
    server.listen(port, hostname, () => {
      console.log(`Server running at http://${hostname}:${port}/`);
    });
    ```
    
    This code creates a basic HTTP server that listens on port 3000 and responds with a "Hello, world!" message to all incoming requests.
    
6. Start your application by running the following command in your terminal or command prompt:
    
    ```bash
    node index.js
    ```
    
    This will start the server and print a message to the console indicating that it's running.
    
7. Open your web browser and navigate to [`http://localhost:3000`](http://localhost:3000). You should see the "Hello, world!" message displayed in your browser.
    

Congratulations! You've just created a simple Node.js application.

## **Building a Simple Backend Project**

Now that you've got a basic understanding of how Node.js works, let's build a simple backend project. We'll create an API that allows you to create, read, update, and delete (CRUD) items in a simple to-do list.

To get started, follow these steps:

1. Create a new directory for your project and navigate to it in your terminal or command prompt.
    
2. Initialize a new Node.js project by running the following command:
    
    ```javascript
    npm init
    ```
    
    This will prompt you to enter some information about your project, such as its name, version, and description. You can accept the default values for most of these prompts by pressing enter, but you can also customize them
    
3. Install the following packages by running the following commands:
    
    ```bash
    npm install express
    npm install body-parser
    npm install cors
    ```
    
    These packages will help us build our backend API. Express is a popular Node.js web framework that provides a set of tools for building web applications, while body-parser is a middleware that parses incoming request bodies and makes them available under `req.body`. Cors is a middleware that enables cross-origin resource sharing (CORS) and allows our front end to access our backend API.
    
4. Create a new file called `server.js` in your project directory. This will be the entry point for your application.
    
5. Open `server.js` in your code editor and add the following code:
    
    ```javascript
    const express = require('express');
    const bodyParser = require('body-parser');
    const cors = require('cors');
    
    const app = express();
    const port = 3000;
    
    let todoList = [
      { id: 1, task: 'Buy groceries' },
      { id: 2, task: 'Walk the dog' },
      { id: 3, task: 'Do laundry' }
    ];
    
    app.use(bodyParser.json());
    app.use(cors());
    
    app.get('/api/todo', (req, res) => {
      res.json(todoList);
    });
    
    app.post('/api/todo', (req, res) => {
      const todo = {
        id: todoList.length + 1,
        task: req.body.task
      };
    
      todoList.push(todo);
      res.json(todo);
    });
    
    app.put('/api/todo/:id', (req, res) => {
      const todo = todoList.find(t => t.id === parseInt(req.params.id));
      if (!todo) return res.status(404).send('The todo with the given ID was not found.');
    
      todo.task = req.body.task;
      res.json(todo);
    });
    
    app.delete('/api/todo/:id', (req, res) => {
      const todo = todoList.find(t => t.id === parseInt(req.params.id));
      if (!todo) return res.status(404).send('The todo with the given ID was not found.');
    
      const index = todoList.indexOf(todo);
      todoList.splice(index, 1);
    
      res.json(todo);
    });
    
    app.listen(port, () => {
      console.log(`Server running at http://localhost:${port}`);
    });
    ```
    
    This code creates a basic Express server that listens on port 3000 and provides API endpoints for creating, reading, updating, and deleting to-do items. The `todoList` variable is an array of to-do items that we'll use as our data store.
    
6. Start your application by running the following command in your terminal or command prompt:
    
    ```bash
    node server.js
    ```
    
    This will start the server and print a message to the console indicating that it's running.
    
7. Open your web browser and navigate to [`http://localhost:3000/api/todo`](http://localhost:3000/api/todo). You should see a JSON response containing the default to-do list items.
    
8. You can use a tool like Postman or curl to make HTTP requests to the API endpoints and manipulate the to-do list items. For example, to create a new to-do item, you can send a POST request to [`http://localhost:3000/api/todo`](http://localhost:3000/api/todo) with a JSON payload like this:
    
    ```bash
    {
      "task": "Clean the house"
    }
    ```
    
    This will create a new to-do item with a unique ID and the specified task. Similarly, you can use PUT requests to update existing to-do items and DELETE requests to delete them.