---
title: "Introduction to Stacks - Basics and Operations | Data Structures and Algorithms Day #6"
seoTitle: "Introduction to Stacks - Basics and Operations | Day #6"
seoDescription: "Learn the basics of the stack data structure with operations like push, pop, and peek. Explore Python and JavaScript examples and discover the real-world..."
datePublished: Mon Oct 07 2024 21:00:32 GMT+0000 (Coordinated Universal Time)
cuid: cm1zhxo4k00000al8gs3c2xfd
slug: introduction-to-stacks-basics-and-operations-data-structures-and-algorithms-day-6
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1727972249580/eea682a6-eba1-49f6-935e-3d53a6d75f82.png
tags: productivity, algorithms, software-development, programming-blogs, programming, web-development, software-architecture, data-structures, webdev, coding, software-engineering, programming-languages, web3, programming-tips, wemakedevs

---

Stacks are a **fundamental** [**data structure**](https://hojaleaks.com/what-are-data-structures-data-structures-and-algorithms-day-1) in programming, offering a simple yet powerful way to manage data. They are widely used in algorithms, from **expression parsing to undo operations** in text editors. In this article, we’ll explore the **basics of stacks**, demonstrate key **operations like push, pop, and peek** with **Python and JavaScript examples**, and discuss their real-world applications. By the end, you’ll understand how to implement a stack, its time complexity, and common use cases.

---

## **What is a Stack?**

A **stack data structure** is a collection of elements that follows the **LIFO (Last-In, First-Out) principle**. This means that the last element added to the stack is the first one to be removed. Imagine a stack of plates: the plate placed on top is the first to be removed.

### **Key Characteristics of Stacks**

* **LIFO Principle:** The last inserted element is accessed first.
    
* **Sequential Access:** You can only access the topmost element without removing others.
    
* **Dynamic Size:** Can grow or shrink dynamically based on operations.
    

---

## **Operations on Stacks**

Here are the core operations performed on a stack:

### **1\. Push Operation**

Adds an element to the top of the stack.

**Python Example:**

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)

stack = Stack()
stack.push(5)  # Adds 5 to the stack
stack.push(10) # Adds 10 on top
print(stack.items)  # Output: [5, 10]
```

**JavaScript Example:**

```javascript
class Stack {
    constructor() {
        this.items = [];
    }

    push(item) {
        this.items.push(item);
    }
}

const stack = new Stack();
stack.push(5);  // Adds 5 to the stack
stack.push(10); // Adds 10 on top
console.log(stack.items);  // Output: [5, 10]
```

---

### **2\. Pop Operation**

Removes the top element from the stack.

**Python Example:**

```python
def pop(self):
    return self.items.pop() if not self.is_empty() else None
```

**JavaScript Example:**

```javascript
pop() {
    return this.items.length > 0 ? this.items.pop() : null;
}
```

---

### **3\. Peek Operation**

Returns the top element without removing it.

**Python Example:**

```python
def peek(self):
    return self.items[-1] if not self.is_empty() else None
```

**JavaScript Example:**

```javascript
peek() {
    return this.items.length > 0 ? this.items[this.items.length - 1] : null;
}
```

---

### **4\. isEmpty Operation**

Checks if the stack is empty.

**Python Example:**

```python
def is_empty(self):
    return len(self.items) == 0
```

**JavaScript Example:**

```javascript
isEmpty() {
    return this.items.length === 0;
}
```

---

## **Diagram: Stack Operations**

Below is a visual representation of how **push and pop operations** work on a stack.

1. **Push:** Add elements to the top.
    
2. **Pop:** Remove the top element.
    

## [**Time Complexity**](https://hojaleaks.com/understanding-time-complexity-big-o-notation-part-1-data-structures-and-algorithms) **of Stack Operations**

| **Operation** | **Time Complexity** |
| --- | --- |
| Push | O(1) |
| Pop | O(1) |
| Peek | O(1) |
| isEmpty | O(1) |

Since all operations only involve the **top element**, stacks are extremely efficient with **O(1) time complexity**.

---

## **Real-World Applications of Stacks**

Stacks are used in various programming scenarios, including:

* **Undo/Redo Operations:** Text editors use stacks to track user actions.
    
* **Expression Parsing:** Stacks help in evaluating arithmetic expressions or handling parentheses.
    
* **Call Stacks:** Programming languages manage function calls using a stack.
    
* **Browser History:** Backtracking through visited pages uses a stack.
    

---

## **Types of Stacks: Static vs. Dynamic**

| **Static Stack** | **Dynamic Stack** |
| --- | --- |
| Fixed-size, limited space | Grows dynamically with new elements |
| Example: Array-based stack | Example: Linked list-based stack |

---

## **Common Misconceptions about Stacks**

1. **"Stacks are only for storing integers."**  
    Stacks can store any data type, including strings and objects.
    
2. **"Stacks are always inefficient."**  
    While not ideal for all scenarios, stacks offer **O(1) time complexity** for most operations, making them highly efficient for specific use cases.
    

---

For more on related data structures, check out:

* [**Queues vs. Stacks**](https://www.geeksforgeeks.org/difference-between-stack-and-queue-data-structures/)
    
* [**Recursion and Stacks in Programming**](https://www.freecodecamp.org/news/how-recursion-works-explained-with-flowcharts-and-a-video-de61f40cb7f9/)
    

---

## **FAQ Section**

### **What is the difference between push and pop operations?**

* **Push:** Adds an element to the top of the stack.
    
* **Pop:** Removes the top element from the stack.
    

### **How is a stack implemented in** [**Python**](https://hojaleaks.com/series/python)**?**

Stacks in Python can be implemented using **lists** or the **deque module** from the collections library.

### **What are the common uses of stacks in real-world applications?**

Stacks are used in **undo operations**, **expression parsing**, and **managing function calls** through the **call stack**.

---

## **Conclusion**

Stacks are an essential data structure that offers **simple and efficient data management** through the [**LIFO principle**](https://hackernoon.com/stacks-in-programming-understanding-the-lifo-data-structure-and-its-applications). With operations like **push, pop, and peek**, stacks are widely used in both **theoretical and practical applications**, such as **expression parsing** and **browser history management**.

Try implementing a **stack** in your preferred programming language using the **examples above**. Understanding how stacks work will not only improve your knowledge of data structures but also help you solve algorithmic problems more efficiently.

---

%[https://youtu.be/kyFtUyO170Y?si=Bnu75pIREbSSCZkK]