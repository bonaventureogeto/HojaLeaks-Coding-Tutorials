---
title: "Types of Queues: Simple, Circular, and Priority Queues | Data Structures and Algorithms Day #9"
seoTitle: "Types of Queues: Simple, Circular, and Priority Queues | Day #9"
seoDescription: "Explore the different types of queues: simple, circular, and priority. Learn their differences with code examples and real-world applications in Python..."
datePublished: Thu Oct 10 2024 21:00:09 GMT+0000 (Coordinated Universal Time)
cuid: cm23s8ptv000008mk1fbxfcuk
slug: types-of-queues-simple-circular-and-priority-queues-data-structures-and-algorithms-day-9
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1727972919180/674d2a9c-37c6-40e7-be05-e5a157c6e299.png
tags: interview, algorithms, software-development, programming-blogs, programming, javascript, python, web-development, data-structures, webdev, python3, coding, software-engineering, queues, wemakedevs

---

Understanding the **different types of queues** is crucial for mastering data structures. Queues operate based on the **FIFO (First-In-First-Out) principle**, making them essential in situations where elements need to be processed sequentially, such as task scheduling, handling requests, or managing buffers. In this article, we’ll explore the **simple queue, circular queue, and priority queue**, discuss their operations, and look at **Python and JavaScript code examples** for each type.

---

%[https://youtu.be/uMFpDNoYf28?si=EMiW8vUhomdloMOQ] 

## What is a Simple Queue?

A **simple queue**, also called a **linear queue**, is the most basic type of queue. It follows the **FIFO principle**, meaning the first element added is the first to be removed.

### Operations on Simple Queue

1. **Enqueue** – Add an element to the rear of the queue.
    
2. **Dequeue** – Remove an element from the front.
    
3. **Peek** – View the front element without removing it.
    
4. **isEmpty** – Check if the queue is empty.
    

### Python Code Example for Simple Queue

```python
class SimpleQueue:
    def __init__(self):
        self.queue = []

    def enqueue(self, item):
        self.queue.append(item)

    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)
        return "Queue is empty!"

    def peek(self):
        return self.queue[0] if not self.is_empty() else None

    def is_empty(self):
        return len(self.queue) == 0

# Example Usage
q = SimpleQueue()
q.enqueue(1)
q.enqueue(2)
print(q.dequeue())  # Output: 1
```

### JavaScript Code Example for Simple Queue

```javascript
class SimpleQueue {
  constructor() {
    this.queue = [];
  }

  enqueue(item) {
    this.queue.push(item);
  }

  dequeue() {
    return this.queue.length ? this.queue.shift() : "Queue is empty!";
  }

  peek() {
    return this.queue[0] || null;
  }

  isEmpty() {
    return this.queue.length === 0;
  }
}

// Example Usage
const q = new SimpleQueue();
q.enqueue(1);
q.enqueue(2);
console.log(q.dequeue()); // Output: 1
```

---

## Circular Queue

A **circular queue** connects the rear and front of the queue to create a loop, allowing efficient use of space. When the end of the queue is reached, new elements can be added at the beginning if there is space available.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729683574567/5de1c8a9-9c5a-4746-a23b-846794ac6766.png align="center")

### Python Code Example for Circular Queue

```python
class CircularQueue:
    def __init__(self, size):
        self.queue = [None] * size
        self.size = size
        self.front = self.rear = -1

    def enqueue(self, item):
        if (self.rear + 1) % self.size == self.front:
            return "Queue is full!"
        elif self.front == -1:
            self.front = self.rear = 0
        else:
            self.rear = (self.rear + 1) % self.size
        self.queue[self.rear] = item

    def dequeue(self):
        if self.front == -1:
            return "Queue is empty!"
        item = self.queue[self.front]
        if self.front == self.rear:
            self.front = self.rear = -1  # Queue is now empty
        else:
            self.front = (self.front + 1) % self.size
        return item
```

---

## Priority Queue: When Order Matters

A **priority queue** allows elements to be dequeued based on their priority rather than their arrival order. This is useful in scenarios like scheduling or pathfinding algorithms.

### JavaScript Code Example for Priority Queue

```javascript
class PriorityQueue {
  constructor() {
    this.queue = [];
  }

  enqueue(item, priority) {
    const newItem = { item, priority };
    let added = false;

    for (let i = 0; i < this.queue.length; i++) {
      if (this.queue[i].priority > priority) {
        this.queue.splice(i, 0, newItem);
        added = true;
        break;
      }
    }

    if (!added) this.queue.push(newItem);
  }

  dequeue() {
    return this.queue.length ? this.queue.shift() : "Queue is empty!";
  }
}
```

---

## Comparison of Queue Types

| Queue Type | Structure | Use Case |
| --- | --- | --- |
| Simple Queue | Linear | General-purpose FIFO processing |
| Circular Queue | Circular, with wrapped ends | Efficient memory usage |
| Priority Queue | Based on priority, not FIFO | Task scheduling, pathfinding |

---

## Time Complexities of Queue Operations

| Operation | Simple Queue | Circular Queue | Priority Queue |
| --- | --- | --- | --- |
| Enqueue | O(1) | O(1) | O(n) |
| Dequeue | O(1) | O(1) | O(1) |
| Peek | O(1) | O(1) | O(1) |

---

## Real-World Applications

* **Simple Queue**: Printer job scheduling, task management.
    
* **Circular Queue**: Memory management in embedded systems.
    
* **Priority Queue**: Task scheduling in operating systems and Dijkstra’s algorithm.
    

---

## FAQs

1. ### What is the difference between a circular and simple queue?
    

A circular queue wraps around when the end is reached, utilizing empty spaces more efficiently.

2. ### How does a priority queue work?
    

A priority queue processes elements based on their priority rather than the order of insertion.

3. ### What are some real-world uses of priority queues?
    

They are used in task scheduling, network routing, and shortest path algorithms.

---

## Conclusion

Try implementing these **queue types in Python or JavaScript** using the code examples provided, and explore their applications further in your projects.