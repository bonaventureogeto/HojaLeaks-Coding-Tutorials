---
title: "JavaScript In 5 Days"
seoTitle: "JavaScript in 5 Days"
datePublished: Wed Jul 24 2024 10:40:40 GMT+0000 (Coordinated Universal Time)
cuid: clyzprm8g00040akygw7k8qh7
slug: javascript-in-5-days
tags: javascript

---

### Day 1: Introduction to JavaScript and Basic Concepts

#### Tutorial 1: Setting Up the Development Environment

1. **Install Visual Studio Code (VSCode):**
    
    * **Step 1:** Go to the [VSCode official website](https://code.visualstudio.com/).
        
    * **Step 2:** Download the installer for your operating system (Windows, macOS, or Linux).
        
    * **Step 3:** Run the installer and follow the on-screen instructions to complete the installation.
        
    * **Step 4:** Open VSCode after installation.
        
2. **Install Node.js:**
    
    * **Step 1:** Visit the [Node.js official website](https://nodejs.org/).
        
    * **Step 2:** Download the LTS (Long Term Support) version for your operating system.
        
    * **Step 3:** Run the installer and follow the on-screen instructions to install Node.js.
        
    * **Step 4:** Verify the installation by opening a terminal (Command Prompt on Windows, Terminal on macOS/Linux) and typing `node -v`. You should see the version number of Node.js.
        
3. **Open VSCode and Set Up a New Project:**
    
    * **Step 1:** Open VSCode.
        
    * **Step 2:** Create a new folder for your JavaScript projects. You can name it something like `JavaScriptProjects`.
        
    * **Step 3:** In VSCode, click on `File` -&gt; `Open Folder` and select the folder you just created.
        
    * **Step 4:** Open the terminal in VSCode by pressing `Ctrl +` (backtick) or going to `View` -&gt; `Terminal`.
        

#### Tutorial 2: JavaScript Basics

1. **Creating Your First JavaScript File:**
    
    * **Step 1:** In your project folder, create a new file called `index.js`.
        
    * **Step 2:** Open `index.js` and write the following code:
        
        ```javascript
        console.log('Hello, JavaScript!');
        ```
        
    * **Step 3:** Save the file.
        
    * **Step 4:** In the terminal, navigate to the folder containing `index.js` and run the file using the command:
        
        ```plaintext
        node index.js
        ```
        
    * **Step 5:** You should see `Hello, JavaScript!` printed in the terminal.
        
2. **Variables and Data Types:**
    
    * **Variables:**
        
        * **Step 1:** In `index.js`, declare variables using `let`, `const`, and `var`.
            
        * **Step 2:** Understand the differences between them:
            
            ```javascript
            let age = 25; // Can be reassigned
            const name = 'John'; // Cannot be reassigned
            var isStudent = true; // Function-scoped, older way of declaring variables
            ```
            
    * **Data Types:**
        
        * **Step 1:** Explore different data types by writing the following code in `index.js`:
            
            ```javascript
            let number = 10; // Number
            let text = 'Hello'; // String
            let isTrue = false; // Boolean
            let nothing = null; // Null
            let notDefined; // Undefined
            let person = { name: 'Alice', age: 30 }; // Object
            ```
            
        * **Step 2:** Use `console.log` to print these variables and their types:
            
            ```javascript
            console.log(typeof number); // number
            console.log(typeof text); // string
            console.log(typeof isTrue); // boolean
            console.log(typeof nothing); // object (null is an object)
            console.log(typeof notDefined); // undefined
            console.log(typeof person); // object
            ```
            
3. **Operators and Expressions:**
    
    * **Step 1:** Practice using different operators by writing the following code:
        
        ```javascript
        let sum = 5 + 3; // Arithmetic
        let difference = 10 - 6;
        let product = 4 * 2;
        let quotient = 8 / 2;
        
        let isEqual = (5 == '5'); // Comparison (true because of type coercion)
        let isIdentical = (5 === '5'); // Strict comparison (false)
        
        let isAdult = (age > 18) && isStudent; // Logical
        let isMinor = (age < 18) || isStudent;
        let isNotStudent = !isStudent;
        ```
        

#### Tutorial 3: Control Structures

1. **Conditionals:**
    
    * **Step 1:** Write `if`, `else if`, and `else` statements:
        
        ```javascript
        let age = 20;
        
        if (age >= 18) {
          console.log('Adult');
        } else if (age >= 13) {
          console.log('Teenager');
        } else {
          console.log('Child');
        }
        ```
        
    * **Step 2:** Use a `switch` statement for multiple conditions:
        
        ```javascript
        let day = 'Monday';
        
        switch (day) {
          case 'Monday':
            console.log('Start of the week');
            break;
          case 'Wednesday':
            console.log('Midweek');
            break;
          case 'Friday':
            console.log('Weekend is near');
            break;
          default:
            console.log('Other day');
        }
        ```
        
2. **Loops:**
    
    * **For Loop:**
        
        * **Step 1:** Write a `for` loop to print numbers from 0 to 4:
            
            ```javascript
            for (let i = 0; i < 5; i++) {
              console.log(i);
            }
            ```
            
    * **While Loop:**
        
        * **Step 1:** Write a `while` loop to print numbers from 5 to 1:
            
            ```javascript
            let count = 5;
            while (count > 0) {
              console.log(count);
              count--;
            }
            ```
            
    * **Do...While Loop:**
        
        * **Step 1:** Write a `do...while` loop to print numbers from 1 to 3:
            
            ```javascript
            let num = 1;
            do {
              console.log(num);
              num++;
            } while (num <= 3);
            ```
            

#### Tutorial 4: Project 1 - Simple Calculator

1. **Basic Calculator Implementation:**
    
    * **Step 1:** Create an HTML file `calculator.html` and link it to a new JavaScript file `calculator.js`:
        
        ```html
        <!DOCTYPE html>
        <html lang="en">
        <head>
          <meta charset="UTF-8">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <title>Simple Calculator</title>
          <script src="calculator.js" defer></script>
        </head>
        <body>
          <h1>Simple Calculator</h1>
        </body>
        </html>
        ```
        
    * **Step 2:** In `calculator.js`, write the basic calculator code:
        
        ```javascript
        let num1 = parseFloat(prompt('Enter first number:'));
        let num2 = parseFloat(prompt('Enter second number:'));
        let operator = prompt('Enter operator (+, -, *, /):');
        let result;
        
        if (operator === '+') {
          result = num1 + num2;
        } else if (operator === '-') {
          result = num1 - num2;
        } else if (operator === '*') {
          result = num1 * num2;
        } else if (operator === '/') {
          result = num1 / num2;
        } else {
          alert('Invalid operator');
        }
        
        alert('Result: ' + result);
        ```
        

### Day 2: Functions and Arrays

#### Tutorial 1: Functions

1. **Declaring and Invoking Functions:**
    
    * **Step 1:** In `index.js`, declare a function:
        
        ```javascript
        function greet(name) {
          return 'Hello, ' + name;
        }
        
        console.log(greet('Alice'));
        ```
        
    * **Step 2:** Understand parameters and return values:
        
        ```javascript
        function add(a, b) {
          return a + b;
        }
        
        let sum = add(3, 5);
        console.log(sum);
        ```
        
2. **Arrow Functions:**
    
    * **Step 1:** Rewrite the `add` function as an arrow function:
        
        ```javascript
        const add = (a, b) => a + b;
        console.log(add(3, 5));
        ```
        

#### Tutorial 2: Arrays

1. **Creating and Manipulating Arrays:**
    
    * **Step 1:** Create an array and access its elements:
        
        ```javascript
        let numbers = [1, 2, 3, 4, 5];
        console.log(numbers[0]); // 1
        console.log(numbers[4]); // 5
        ```
        
    * **Step 2:** Use array methods like `push`, `pop`, `shift`, `unshift`:
        
        ```javascript
        numbers.push(6);
        console.log(numbers); // [1, 2, 3, 4, 5, 6]
        
        numbers.pop();
        console.log(numbers); // [1, 2, 3, 4, 5]
        
        numbers.shift();
        console.log(numbers); // [2, 3, 4, 5]
        
        numbers.unshift(1);
        console.log(numbers); // [1, 2, 3, 4, 5]
        ```
        
2. **Array Methods:**
    
    * Step 1: Use `map` to create a new array with each element doubled: `javascript let doubled =`[`numbers.map`](http://numbers.map)`(num => num * 2); console.log(doubled); // [2, 4, 6, 8, 10]`
        
    * **Step 2:** Use `filter` to create a new array with even numbers:
        
    
    ```javascript
    let evenNumbers = numbers.filter(num => num % 2 === 0);
    console.log(evenNumbers); // [2, 4]
    ```
    
    **Step 3:** Use `reduce` to sum all the numbers in the array:
    
    ```javascript
    let sum = numbers.reduce((acc, num) => acc + num, 0);
    console.log(sum); // 15
    ```
    

#### Tutorial 3: Project 1 Enhancements

1. **Modularize Calculator Code:**
    
    * **Step 1:** Refactor the calculator code to use functions for different operations:
        
        ```javascript
        function add(a, b) {
          return a + b;
        }
        
        function subtract(a, b) {
          return a - b;
        }
        
        function multiply(a, b) {
          return a * b;
        }
        
        function divide(a, b) {
          return a / b;
        }
        
        function calculate(num1, num2, operator) {
          switch (operator) {
            case '+':
              return add(num1, num2);
            case '-':
              return subtract(num1, num2);
            case '*':
              return multiply(num1, num2);
            case '/':
              return divide(num1, num2);
            default:
              return 'Invalid operator';
          }
        }
        
        let num1 = parseFloat(prompt('Enter first number:'));
        let num2 = parseFloat(prompt('Enter second number:'));
        let operator = prompt('Enter operator (+, -, *, /):');
        let result = calculate(num1, num2, operator);
        alert('Result: ' + result);
        ```
        

### Day 3: Objects and DOM Manipulation

#### Tutorial 1: Objects

1. **Creating and Using Objects:**
    
    * **Step 1:** Create an object and access its properties and methods:
        
        ```javascript
        let person = {
          name: 'Alice',
          age: 25,
          greet() {
            console.log('Hello, ' + this.name);
          }
        };
        
        console.log(person.name); // Alice
        person.greet(); // Hello, Alice
        ```
        

#### Tutorial 2: DOM Manipulation

1. **Selecting and Modifying DOM Elements:**
    
    * **Step 1:** Create an HTML file `dom.html` and link it to a new JavaScript file `dom.js`:
        
        ```html
        <!DOCTYPE html>
        <html lang="en">
        <head>
          <meta charset="UTF-8">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <title>DOM Manipulation</title>
          <script src="dom.js" defer></script>
        </head>
        <body>
          <h1 id="header">Hello, World!</h1>
          <button id="changeColorButton">Change Color</button>
        </body>
        </html>
        ```
        
    * **Step 2:** In `dom.js`, select and modify the header element:
        
        ```javascript
        let header = document.getElementById('header');
        header.textContent = 'New Header';
        header.style.color = 'blue';
        ```
        
2. **Event Handling:**
    
    * **Step 1:** Add an event listener to the button to change the header color when clicked:
        
        ```javascript
        let button = document.getElementById('changeColorButton');
        button.addEventListener('click', () => {
          header.style.color = 'red';
        });
        ```
        

#### Tutorial 3: Project 2 - To-Do List Application

1. **Basic To-Do List Implementation:**
    
    * **Step 1:** Create an HTML file `todo.html` and link it to a new JavaScript file `todo.js`:
        
        ```html
        <!DOCTYPE html>
        <html lang="en">
        <head>
          <meta charset="UTF-8">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <title>To-Do List</title>
          <script src="todo.js" defer></script>
        </head>
        <body>
          <h1>To-Do List</h1>
          <input type="text" id="taskInput" placeholder="Add a new task">
          <button id="addTaskButton">Add Task</button>
          <ul id="taskList"></ul>
        </body>
        </html>
        ```
        
    * **Step 2:** In `todo.js`, implement the to-do list functionality:
        
        ```javascript
        let tasks = [];
        
        function addTask(task) {
          tasks.push({ text: task, completed: false });
          renderTasks();
        }
        
        function removeTask(index) {
          tasks.splice(index, 1);
          renderTasks();
        }
        
        function toggleTask(index) {
          tasks[index].completed = !tasks[index].completed;
          renderTasks();
        }
        
        function renderTasks() {
          let taskList = document.getElementById('taskList');
          taskList.innerHTML = '';
          tasks.forEach((task, index) => {
            let li = document.createElement('li');
            li.textContent = task.text;
            if (task.completed) {
              li.style.textDecoration = 'line-through';
            }
            li.addEventListener('click', () => toggleTask(index));
            let removeButton = document.createElement('button');
            removeButton.textContent = 'Remove';
            removeButton.addEventListener('click', () => removeTask(index));
            li.appendChild(removeButton);
            taskList.appendChild(li);
          });
        }
        
        document.getElementById('addTaskButton').addEventListener('click', () => {
          let taskInput = document.getElementById('taskInput');
          let taskText = taskInput.value;
          if (taskText) {
            addTask(taskText);
            taskInput.value = '';
          }
        });
        ```
        

### Day 4: Advanced Concepts and ES6 Features

#### Tutorial 1: Advanced Functions

1. **Higher-Order Functions:**
    
    * **Step 1:** Write a function that accepts another function as an argument:
        
        ```javascript
        function applyOperation(a, b, operation) {
          return operation(a, b);
        }
        
        function add(a, b) {
          return a + b;
        }
        
        console.log(applyOperation(5, 3, add)); // 8
        ```
        
2. **Closures and IIFE:**
    
    * **Step 1:** Understand closures with an example:
        
        ```javascript
        function createCounter() {
          let count = 0;
          return function () {
            count++;
            return count;
          };
        }
        
        let counter = createCounter();
        console.log(counter()); // 1
        console.log(counter()); // 2
        ```
        
    * **Step 2:** Write an Immediately Invoked Function Expression (IIFE):
        
        ```javascript
        (function () {
          console.log('This function runs immediately!');
        })();
        ```
        

#### Tutorial 2: ES6 Features

1. **Template Literals:**
    
    * **Step 1:** Use template literals for string interpolation:
        
        ```javascript
        let name = 'Alice';
        let greeting = `Hello, ${name}`;
        console.log(greeting); // Hello, Alice
        ```
        
2. **Destructuring:**
    
    * **Step 1:** Destructure arrays and objects:
        
        ```javascript
        let [a, b] = [1, 2];
        console.log(a); // 1
        console.log(b); // 2
        
        let person = { name: 'Alice', age: 25 };
        let { name, age } = person;
        console.log(name); // Alice
        console.log(age); // 25
        ```
        
3. **Spread and Rest Operators:**
    
    * **Step 1:** Use the spread operator to expand arrays:
        
        ```javascript
        let arr1 = [1, 2, 3];
        let arr2 = [...arr1, 4, 5];
        console.log(arr2); // [1, 2, 3, 4, 5]
        ```
        
    * **Step 2:** Use the rest operator to collect arguments:
        
        ```javascript
        function sum(...numbers) {
          return numbers.reduce((acc, num) => acc + num, 0);
        }
        
        console.log(sum(1, 2, 3)); // 6
        ```
        
4. **Classes and Inheritance:**
    
    * **Step 1:** Understand ES6 classes and inheritance:
        
        ```javascript
        class Animal {
          constructor(name) {
            this.name = name;
          }
        
          speak() {
            console.log(`${this.name} makes a noise.`);
          }
        }
        
        class Dog extends Animal {
          speak() {
            console.log(`${this.name} barks.`);
          }
        }
        
        let dog = new Dog('Rex');
        dog.speak(); // Rex barks.
        ```
        

#### Tutorial 3: Project 2 Enhancements

1. **Saving to Local Storage:**
    
    * **Step 1:** Use `localStorage` to persist the to-do list across sessions:
        
        ```javascript
        function saveTasks(){ 
            localStorage.setItem('tasks', JSON.stringify(tasks));
        }
        
        function loadTasks() {
            let storedTasks = localStorage.getItem('tasks'); 
            if (storedTasks) {
                tasks = JSON.parse(storedTasks);
                renderTasks();
             } 
        }
        
        loadTasks();
        
        function addTask(task) { tasks.push({ text: task, completed: false }); saveTasks(); renderTasks(); }
        
        function removeTask(index) { tasks.splice(index, 1); saveTasks(); renderTasks(); }
        
        function toggleTask(index) { tasks[index].completed = !tasks[index].completed; saveTasks(); renderTasks(); } ```
        ```
        
2. **Filtering Tasks:**
    
    * **Step 1:** Add buttons to filter tasks (all, completed, incomplete):
        
        ```html
        <button id="allTasksButton">All</button>
        <button id="completedTasksButton">Completed</button>
        <button id="incompleteTasksButton">Incomplete</button>
        ```
        
    * **Step 2:** Implement filtering logic in `todo.js`:
        
        ```javascript
        function filterTasks(filter) {
          let filteredTasks = tasks.filter(task => {
            if (filter === 'all') return true;
            if (filter === 'completed') return task.completed;
            if (filter === 'incomplete') return !task.completed;
          });
          renderTasks(filteredTasks);
        }
        
        document.getElementById('allTasksButton').addEventListener('click', () => filterTasks('all'));
        document.getElementById('completedTasksButton').addEventListener('click', () => filterTasks('completed'));
        document.getElementById('incompleteTasksButton').addEventListener('click', () => filterTasks('incomplete'));
        
        function renderTasks(filteredTasks = tasks) {
          let taskList = document.getElementById('taskList');
          taskList.innerHTML = '';
          filteredTasks.forEach((task, index) => {
            let li = document.createElement('li');
            li.textContent = task.text;
            if (task.completed) {
              li.style.textDecoration = 'line-through';
            }
            li.addEventListener('click', () => toggleTask(index));
            let removeButton = document.createElement('button');
            removeButton.textContent = 'Remove';
            removeButton.addEventListener('click', () => removeTask(index));
            li.appendChild(removeButton);
            taskList.appendChild(li);
          });
        }
        ```
        

### Day 5: APIs and Final Touches

#### Tutorial 1: Working with APIs

1. **Fetch API:**
    
    * **Step 1:** Learn how to make GET requests using the Fetch API:
        
        ```javascript
        fetch('https://api.example.com/data')
          .then(response => response.json())
          .then(data => console.log(data))
          .catch(error => console.error('Error:', error));
        ```
        
    * **Step 2:** Learn how to make POST requests using the Fetch API:
        
        ```javascript
        fetch('https://api.example.com/data', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({ key: 'value' })
        })
          .then(response => response.json())
          .then(data => console.log(data))
          .catch(error => console.error('Error:', error));
        ```
        
2. **Async/Await:**
    
    * **Step 1:** Use async functions and handle errors with try/catch:
        
        ```javascript
        async function fetchData() {
          try {
            let response = await fetch('https://api.example.com/data');
            let data = await response.json();
            console.log(data);
          } catch (error) {
            console.error('Error:', error);
          }
        }
        
        fetchData();
        ```
        

#### Tutorial 2: Project 2 Final Enhancements

1. **Integrating Weather API:**
    
    * **Step 1:** Use a weather API to display the weather for each task location:
        
        ```javascript
        async function getWeather(location) {
          let response = await fetch(`https://api.weatherapi.com/v1/current.json?key=YOUR_API_KEY&q=${location}`);
          let data = await response.json();
          return data.current.temp_c;
        }
        
        async function addTaskWithWeather(task, location) {
          let weather = await getWeather(location);
          tasks.push({ text: task, location: location, weather: weather, completed: false });
          saveTasks();
          renderTasks();
        }
        
        document.getElementById('addTaskButton').addEventListener('click', async () => {
          let taskInput = document.getElementById('taskInput');
          let locationInput = document.getElementById('locationInput');
          let taskText = taskInput.value;
          let locationText = locationInput.value;
          if (taskText && locationText) {
            await addTaskWithWeather(taskText, locationText);
            taskInput.value = '';
            locationInput.value = '';
          }
        });
        ```
        

**README for To-Do List Application:**

```markdown
# To-Do List Application

## Description
This is a simple to-do list application that allows users to add, remove, and mark tasks as completed. It also integrates a weather API to display the weather for each task location.

## Features
- Add new tasks
- Remove tasks
- Mark tasks as completed
- Filter tasks (all, completed, incomplete)
- Save tasks to local storage
- Display weather for each task location

## Usage
1. Open `todo.html` in a web browser.
2. Enter a new task and its location, then click "Add Task".
3. The task will be added to the list and the weather for the location will be displayed.

## Technologies Used
- HTML
- CSS
- JavaScript
- Fetch API
- Local Storage

## License
This project is licensed under the MIT License.
```

This detailed tutorial ensures a comprehensive understanding of JavaScript basics, advanced concepts, and project development, making the learning process engaging and practical.