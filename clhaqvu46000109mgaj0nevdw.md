---
title: "How To Build a Task Manager API with NodeJS, Express, MongoDB, and Heroku"
seoTitle: "Build a Task Manager API with NodeJS, Express, MongoDB, and Heroku"
seoDescription: "This article provides a step-by-step guide on how to build and deploy a Task Manager API using popular technologies such as NodeJS, Express, MongoDB, Heroku"
datePublished: Fri May 05 2023 16:02:42 GMT+0000 (Coordinated Universal Time)
cuid: clhaqvu46000109mgaj0nevdw
slug: how-to-build-a-task-manager-api-with-nodejs
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/iJg1YzsEfqo/upload/ef4edaf9287bbbff8308f07a87c104c6.jpeg
tags: express, javascript, mongodb, nodejs, apis

---

1. Requirements
    
2. Getting Started
    
3. Setting up the basic structure
    
4. Creating Task and User Models
    
5. Creating endpoints and testing with Postman
    
6. Deploying to Heroku
    

## **Requirements**

To follow this tutorial, you'll need the following:

* Node.js installed on your computer
    
* A code editor like Visual Studio Code or Sublime Text
    
* A good understanding of JavaScript:
    
    * [The Fundamentals of JavaScript](https://hojaleaks.com/javascript-101)
        
    * [Object Oriented Programming in JavaScript](https://hojaleaks.com/object-oriented-programming-in-javascript-101-a-complete-guide)
        
    * [Understanding Promises, Async & Await](https://hojaleaks.com/javascript-101-understanding-promises-async-await)
        
    * [How to integrate APIs in vanilla JavaScript](https://hojaleaks.com/tutorial-how-to-integrate-apis-in-vanilla-javascript)
        
    * Bonus Tutorial: [Building a Dynamic Weather Applications using JavaScript DOM](https://hojaleaks.com/building-a-dynamic-weather-application-using-the-javascript-dom)
        

## **Getting started**

1. Create a new directory for your project and navigate to it in your terminal or command prompt:
    
    ```bash
    mkdir task-manager-app
    cd task-manager-app
    ```
    
2. Initialize a new Node.js project by running the following command:
    
    ```bash
    npm init
    ```
    
    This will create a new `package.json` file in your project directory that contains information about your project and its dependencies.
    
3. Install the following packages by running the following commands:
    
    ```bash
    npm install express
    npm install mongoose
    npm install bcrypt
    npm install jsonwebtoken
    npm install dotenv
    npm install multer
    ```
    
    These packages will help us build our task management application. Express is a popular Node.js web framework that provides a set of tools for building web applications, while Mongoose is an Object Data Modeling (ODM) library for MongoDB that provides a higher-level abstraction over the MongoDB Node.js driver. Bcrypt is a library for hashing passwords, while Jsonwebtoken is a library for creating and verifying JSON Web Tokens (JWTs). Dotenv is a zero-dependency module that loads environment variables from a `.env` file, and Multer is a middleware for handling file uploads.
    
4. Create a new file called `.env` in your project directory and add the following environment variables:
    
    ```javascript
    PORT=3000
    MONGODB_URL=mongodb://localhost/task-manager
    JWT_SECRET=mysecretkey
    ```
    
    This file will be used to store sensitive information like your MongoDB URL and JWT secret key.
    
    ## Setting up the Basic Structure for our Task Manager API
    
5. Create a new directory called `src` in your project directory. This will be the directory where you'll write your application code.
    
6. Create a new file called `server.js` in the `src` directory. This will be the entry point for your application.
    
7. Open `server.js` in your code editor and add the following code:
    
    ```javascript
    require('dotenv').config();
    const express = require('express');
    const mongoose = require('mongoose');
    const bodyParser = require('body-parser');
    const multer = require('multer');
    const bcrypt = require('bcrypt');
    const jwt = require('jsonwebtoken');
    
    const app = express();
    const port = process.env.PORT || 3000;
    
    // Connect to MongoDB
    mongoose.connect(process.env.MONGODB_URL, {
      useNewUrlParser: true,
      useUnifiedTopology: true,
      useCreateIndex: true,
      useFindAndModify: false
    }).then(() => {
      console.log('Connected to MongoDB');
    }).catch(error => {
      console.error(error);
    });
    
    // Middleware
    app.use(bodyParser.json());
    app.use(bodyParser.urlencoded({ extended: true }));
    
    // Routes
    app.get('/', (req, res) => {
      res.send('Task Manager API');
    });
    
    // Start the server
    app.listen(port, () => {
      console.log(`Server running at http://localhost:${port}`);
    });
    ```
    
    This code sets up the basic structure for your application. It loads environment variables from the `.env` file using the `dotenv` package, sets up an Express app with some middleware, connects to MongoDB using Mongoose, and starts the server.
    
    Note that we're using the `bcrypt` and `jsonwebtoken` packages for password hashing and authentication. We'll be using them later on when we build the authentication and authorization system for our application.
    
    ## Creating Task and User Models
    
    1. Create a new file called `task.js` in the `src/models` directory. This file will define the `Task` model for our application.
        
        ```javascript
        const mongoose = require('mongoose');
        
        const taskSchema = new mongoose.Schema({
          title: {
            type: String,
            required: true
          },
          description: {
            type: String,
            required: true
          },
          completed: {
            type: Boolean,
            default: false
          },
          dueDate: {
            type: Date
          },
          owner: {
            type: mongoose.Schema.Types.ObjectId,
            required: true,
            ref: 'User'
          }
        }, {
          timestamps: true
        });
        
        const Task = mongoose.model('Task', taskSchema);
        
        module.exports = Task;
        ```
        
        This code defines a `Task` schema with the following properties:
        
        * `title`: A string that represents the title of the task.
            
        * `description`: A string that represents the description of the task.
            
        * `completed`: A boolean that indicates whether the task is completed or not.
            
        * `dueDate`: A date that represents the due date of the task.
            
        * `owner`: A reference to the user who created the task.
            
        
        The `timestamps` option automatically adds `createdAt` and `updatedAt` fields to the schema.
        
    2. Create a new file called `user.js` in the `src/models` directory. This file will define the `User` model for our application.
        
        ```javascript
        const mongoose = require('mongoose');
        const validator = require('validator');
        const bcrypt = require('bcrypt');
        const jwt = require('jsonwebtoken');
        
        const userSchema = new mongoose.Schema({
          name: {
            type: String,
            required: true,
            trim: true
          },
          email: {
            type: String,
            required: true,
            unique: true,
            trim: true,
            lowercase: true,
            validate(value) {
              if (!validator.isEmail(value)) {
                throw new Error('Invalid email address');
              }
            }
          },
          password: {
            type: String,
            required: true,
            trim: true,
            minlength: 6,
            validate(value) {
              if (value.toLowerCase().includes('password')) {
                throw new Error('Password cannot contain "password"');
              }
            }
          },
          tokens: [{
            token: {
              type: String,
              required: true
            }
          }]
        }, {
          timestamps: true
        });
        
        userSchema.virtual('tasks', {
          ref: 'Task',
          localField: '_id',
          foreignField: 'owner'
        });
        
        userSchema.methods.toJSON = function () {
          const user = this.toObject();
        
          delete user.password;
          delete user.tokens;
        
          return user;
        };
        
        userSchema.methods.generateAuthToken = async function () {
          const user = this;
          const token = jwt.sign({ _id: user._id.toString() }, process.env.JWT_SECRET);
        
          user.tokens = user.tokens.concat({ token });
          await user.save();
        
          return token;
        };
        
        userSchema.statics.findByCredentials = async (email, password) => {
          const user = await User.findOne({ email });
        
          if (!user) {
            throw new Error('Invalid email or password');
          }
        
          const isMatch = await bcrypt.compare(password, user.password);
        
          if (!isMatch) {
            throw new Error('Invalid email or password');
          }
        
          return user;
        };
        
        userSchema.pre('save', async function (next) {
          const user = this;
        
          if (user.isModified('password')) {
            user.password = await bcrypt.hash(user.password, 8);
          }
        
          next();
        });
        
        const User = mongoose.model('User', userSchema);
        
        module.exports = User;
        ```
        
        This code defines a `User` schema with the following properties:
        
        * `name`: A string that represents the name of the user.
            
        * `email`: A string that represents the email address of the user.
            
        * `password`: A string that represents the password of the user.
            
        * `tokens`: An array of authentication tokens for the user.
            
        
        The `virtual` method creates a virtual property on the user model that references the tasks owned by the user.
        
        The `toJSON` method is used to remove the `password` and `tokens` fields from the user object before sending it to the client.
        
        The `generateAuthToken` method generates a JWT token and adds it to the user's `tokens` array.
        
        The `findByCredentials` method is used to find a user by email and password.
        
        The `pre` middleware is used to hash the password before saving it to the database.
        
        ## Creating Endpoints for our NodeJS MongoDB API
        
        Now that we have defined the `User` model, we can create the endpoints for our API. Let's create a new file called `user.js` in the `src/routes` directory. In this file, we will define the routes for creating a new user, logging in a user, and logging out a user.
        
        ```javascript
        const express = require('express');
        const User = require('../models/user');
        const auth = require('../middleware/auth');
        
        const router = new express.Router();
        
        // Create a new user
        router.post('/users', async (req, res) => {
          const user = new User(req.body);
        
          try {
            await user.save();
            const token = await user.generateAuthToken();
            res.status(201).send({ user, token });
          } catch (e) {
            res.status(400).send(e);
          }
        });
        
        // Login user
        router.post('/users/login', async (req, res) => {
          try {
            const user = await User.findByCredentials(req.body.email, req.body.password);
            const token = await user.generateAuthToken();
            res.send({ user, token });
          } catch (e) {
            res.status(400).send(e);
          }
        });
        
        // Logout user
        router.post('/users/logout', auth, async (req, res) => {
          try {
            req.user.tokens = req.user.tokens.filter((token) => {
              return token.token !== req.token;
            });
            await req.user.save();
            res.send();
          } catch (e) {
            res.status(500).send(e);
          }
        });
        
        module.exports = router;
        ```
        
        Let's go over what each of these routes does:
        
        * `POST /users`: Creates a new user in the database. The user's information is sent in the request body. If the user is created successfully, the API returns the user's information and a JWT token.
            
        * `POST /users/login`: Logs in a user with their email and password. If the login is successful, the API returns the user's information and a JWT token.
            
        * `POST /users/logout`: Logs out the current user by removing their current authentication token from the `tokens` array in the database. The user must be authenticated to access this route, which is why we use the `auth` middleware.
            
        
        Now that we have our user routes, let's create the task routes. Create a new file called `task.js` in the `src/routes` directory.
        
        ```javascript
        const express = require('express');
        const Task = require('../models/task');
        const auth = require('../middleware/auth');
        
        const router = new express.Router();
        
        // Create a new task
        router.post('/tasks', auth, async (req, res) => {
          const task = new Task({
            ...req.body,
            owner: req.user._id
          });
        
          try {
            await task.save();
            res.status(201).send(task);
          } catch (e) {
            res.status(400).send(e);
          }
        });
        
        // Get all tasks
        router.get('/tasks', auth, async (req, res) => {
          try {
            const tasks = await Task.find({ owner: req.user._id });
            res.send(tasks);
          } catch (e) {
            res.status(500).send(e);
          }
        });
        
        // Get a task by id
        router.get('/tasks/:id', auth, async (req, res) => {
          const _id = req.params.id;
        
          try {
            const task = await Task.findOne({ _id, owner: req.user._id });
        
            if (!task) {
              return res.status(404).send();
            }
        
            res.send(task);
          } catch (e) {
            res.status(500).send(e);
        // Update a task by id
        router.patch('/tasks/:id', auth, async (req, res) => {
          const updates = Object.keys(req.body);
          const allowedUpdates = ['description', 'completed'];
          const isValidOperation = updates.every((update) => allowedUpdates.includes(update));
        
          if (!isValidOperation) {
            return res.status(400).send({ error: 'Invalid updates!' });
          }
        
          try {
            const task = await Task.findOne({ _id: req.params.id, owner: req.user._id });
        
            if (!task) {
              return res.status(404).send();
            }
        
            updates.forEach((update) => task[update] = req.body[update]);
            await task.save();
            res.send(task);
          } catch (e) {
            res.status(400).send(e);
          }
        });
        
        // Delete a task by id
        router.delete('/tasks/:id', auth, async (req, res) => {
          try {
            const task = await Task.findOneAndDelete({ _id: req.params.id, owner: req.user._id });
        
            if (!task) {
              return res.status(404).send();
            }
        
            res.send(task);
          } catch (e) {
            res.status(500).send(e);
          }
        });
        
        module.exports = router;
        ```
        
        Here's what each of these routes does:
        
        * `POST /tasks`: Creates a new task in the database. The task's information is sent in the request body. The `owner` field of the task is set to the ID of the authenticated user. Only authenticated users can access this route.
            
        * `GET /tasks`: Retrieves all tasks from the database that belong to the authenticated user.
            
        * `GET /tasks/:id`: Retrieves a task by its ID from the database if it belongs to the authenticated user.
            
        * `PATCH /tasks/:id`: Updates a task by its ID with the specified fields in the request body. Only the `description` and `completed` fields can be updated. Only authenticated users can update their own tasks.
            
        * `DELETE /tasks/:id`: Deletes a task by its ID if it belongs to the authenticated user.
            
        
        Now that we have our routes defined, let's modify `index.js` to use them:
        
        ```javascript
        const express = require('express');
        require('./db/mongoose');
        const userRouter = require('./routes/user');
        const taskRouter = require('./routes/task');
        
        const app = express();
        const port = process.env.PORT || 3000;
        
        app.use(express.json());
        app.use(userRouter);
        app.use(taskRouter);
        
        app.listen(port, () => {
          console.log(`Server is up on port ${port}`);
        });
        ```
        
        ## Testing Endpoints with Postman or cURL
        
        We're now ready to test our API! You can use tools like Postman or cURL to test the endpoints we defined above. For example, you can create a new user by sending a POST request to [`http://localhost:3000/users`](http://localhost:3000/users) with a JSON body like this:
        
        ```json
        {
          "name": "John Doe",
          "email": "johndoe@example.com",
          "password": "password123"
        }
        ```
        
        You should receive a response with the newly created user's information and a JWT token.
        
        Next, you can use the token to create a new task by sending a POST request to [`http://localhost:3000/tasks`](http://localhost:3000/tasks) with a JSON body like this:
        
        ```json
        {
          "description": "Buy groceries"
        }
        ```
        
        You should receive a response with the newly created task's information.
        
        Finally, you can retrieve all of the user's tasks by sending a GET request to [`http://localhost:3000/tasks`](http://localhost:3000/tasks) with the JWT token in the \`Authorization
        
    
    Now that we have our API up and running, let's take a look at how we can deploy it to a production environment.
    
    ## **Deployment to a Production Environment**
    
    There are many ways to deploy a Node.js application to a production environment, but one of the most popular ways is to use a Platform as a Service (PaaS) provider like Heroku or AWS Elastic Beanstalk. In this tutorial, we'll be using Heroku to deploy our application.
    
    ### **Heroku**
    
    Heroku is a cloud platform that allows you to deploy, manage, and scale your applications. To use Heroku, you'll need to create an account and install the Heroku CLI on your computer. Once you've done that, you can use the following commands to deploy your application:
    
    1. First, create a new Heroku application by running the following command:
        
    
    ```bash
    heroku create
    ```
    
    This will create a new Heroku application and add a new remote to your local Git repository.
    
    1. Next, push your code to the Heroku remote by running the following command:
        
    
    ```bash
    git push heroku main
    ```
    
    This will deploy your application to Heroku.
    
    1. Finally, start your application by running the following command:
        
    
    ```bash
    heroku ps:scale web=1
    ```
    
    This will start a single instance of your application on Heroku.
    
    That's it! Your application should now be live on Heroku.
    
    ### **Environment Variables**
    
    When deploying your application to a production environment, it's important to keep your secrets (like database passwords and JWT secrets) secure. One way to do this is to use environment variables.
    
    To use environment variables in your application, you can use the `dotenv` package. This package allows you to store your environment variables in a `.env` file in your project directory, which is ignored by Git. To use `dotenv`, install it by running the following command:
    
    ```bash
    npm install dotenv
    ```
    
    Then, create a new file called `.env` in your project directory and add your environment variables like this:
    
    ```javascript
    PORT=3000
    MONGODB_URL=mongodb://localhost:27017/task-manager-api
    JWT_SECRET=mysecretkey
    ```
    
    Finally, modify `index.js` to use the `dotenv` package:
    
    ```javascript
    require('dotenv').config();
    const express = require('express');
    require('./db/mongoose');
    const userRouter = require('./routes/user');
    const taskRouter = require('./routes/task');
    
    const app = express();
    const port = process.env.PORT || 3000;
    
    app.use(express.json());
    app.use(userRouter);
    app.use(taskRouter);
    
    app.listen(port, () => {
      console.log(`Server is up on port ${port}`);
    });
    ```
    
    Now, when you deploy your application to a production environment, you can set your environment variables using the provider's interface (for example, Heroku allows you to set environment variables using the Heroku Dashboard or the Heroku CLI).
    
    ## **Conclusion**
    
    In this tutorial, we've covered a lot of ground! We started by building a simple Node.js application that uses Express, Mongoose, and JWT authentication to manage tasks for users. Then, we added more advanced features like middleware, file uploads, and error handling. Finally, we deployed our application to a production environment using Heroku.
    
    There's a lot more to learn about Node.js and web development in general, but hopefully, this tutorial has given you a good starting point.
    
    I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)
    
    Happy coding!