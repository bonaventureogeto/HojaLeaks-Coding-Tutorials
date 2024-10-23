---
title: "How to Reverse a Linked List: Step-by-Step Guide with Code Examples | Day #5"
seoTitle: "How to Reverse a Linked List | Data Structures and Algorithms Day #5"
seoDescription: "Learn how to reverse a linked list with detailed examples in Python and JavaScript. Understand iterative and recursive techniques, time complexity, and..."
datePublished: Sun Oct 06 2024 21:00:52 GMT+0000 (Coordinated Universal Time)
cuid: cm1y2i8fp000109jsf3ps6tve
slug: how-to-reverse-a-linked-list-step-by-step-guide-with-code-examples-day-5
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1727972036877/c4949142-fb13-476a-ad68-bec5def02eb0.png
tags: algorithms, software-development, programming-blogs, programming, python, web-development, data-structures, webdev, coding, software-engineering, web3, leetcode, linkedlists, leetcode-solution, wemakedevs

---

## Why Reversing a Linked List is Essential

In programming and algorithm development, the ability to reverse a linked list is a fundamental skill. Whether working with singly or doubly linked lists, understanding how to reverse them efficiently is crucial in scenarios where you need to rearrange data for optimized access or traversal. This article provides a **comprehensive guide on** [**how to reverse a linked list**](https://youtu.be/E1dnkjd3nAc?si=VDRwCIK_NkGwKXYB), complete with diagrams, **code examples in Python and JavaScript**, and insights into **time complexity** and **in-place reversal**.

By the end of this article, you’ll be able to implement both **iterative and recursive techniques** for reversing linked lists, ensuring you can handle any data structure challenge confidently.

---

## What is a Linked List?

A **linked list** is a linear data structure made up of nodes, where each node contains:

1. **Data** – The actual data value.
    
2. **Pointer** – A reference to the next node (in singly linked lists) or both previous and next nodes (in doubly linked lists).
    

There are **two main types of linked lists**:

* **Singly Linked List:** Nodes point only to the next node.
    
* **Doubly Linked List:** Nodes point to both the previous and next nodes.
    

---

## H2: How to Reverse a Singly Linked List

Reversing a **singly linked list** involves rearranging the pointers of each node so that the direction of traversal is reversed.

### Code Example (Python) – Iterative Approach

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def reverse_linked_list(head):
    previous = None
    current = head

    while current:
        next_node = current.next  # Store next node
        current.next = previous   # Reverse the pointer
        previous = current        # Move 'previous' one step forward
        current = next_node       # Move 'current' one step forward

    return previous

# Example usage
head = Node(1)
head.next = Node(2)
head.next.next = Node(3)

reversed_head = reverse_linked_list(head)
```

### Code Example (JavaScript) – Iterative Approach

```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}

function reverseLinkedList(head) {
  let previous = null;
  let current = head;

  while (current !== null) {
    let nextNode = current.next;
    current.next = previous;
    previous = current;
    current = nextNode;
  }

  return previous;
}

// Example usage
let head = new Node(1);
head.next = new Node(2);
head.next.next = new Node(3);

let reversedHead = reverseLinkedList(head);
```

---

### Diagram of Singly Linked List Reversal

Below is a step-by-step visualization of reversing a singly linked list:

**Initial List:**  
`1 -> 2 -> 3 -> NULL`

**Step 1:**  
`NULL <- 1 2 -> 3 -> NULL`

**Step 2:**  
`NULL <- 1 <- 2 3 -> NULL`

**Final Reversed List:**  
`NULL <- 1 <- 2 <- 3`  
`Reversed List: 3 -> 2 -> 1 -> NULL`

---

## How to Reverse a Doubly Linked List

In a **doubly linked list**, each node has pointers to both the **previous** and **next** nodes. Reversing it involves swapping the `next` and `previous` pointers for each node.

### Code Example (Python) – In-Place Reversal

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

def reverse_doubly_linked_list(head):
    current = head
    while current:
        current.prev, current.next = current.next, current.prev  # Swap pointers
        head = current
        current = current.prev  # Move to the previous node (which is the original next)

    return head

# Example usage
head = Node(1)
head.next = Node(2)
head.next.prev = head
head.next.next = Node(3)
head.next.next.prev = head.next

reversed_head = reverse_doubly_linked_list(head)
```

---

### Time Complexity of Reversing a Linked List

Reversing a linked list—whether singly or doubly—has the following time and space complexities:

* **Time Complexity:** O(n)  
    Every node must be visited once, making the time complexity linear.
    
* **Space Complexity:** O(1)  
    The reversal is done **in-place**, meaning no additional space is required beyond a few pointers.
    

---

## Common Misconceptions about Reversing Linked Lists

1. **"Reversing always requires extra space."**
    
    * In-place reversal only uses a few extra pointers, keeping space complexity O(1).
        
2. **"Reversing a doubly linked list is faster than a singly linked list."**
    
    * Both operations have the same time complexity of O(n).
        
3. **"Iterative reversal is always better than recursive."**
    
    * While iterative reversal avoids stack overflow issues, recursion can make the code cleaner and easier to read for small lists.
        

---

## FAQs:

### 1\. How to reverse a singly linked list?

Use an **iterative approach** by rearranging the `next` pointers of the nodes. A recursive approach can also work but requires extra stack space.

### 2\. What is the [time complexity](https://youtu.be/0Bzw3yDbsyU?si=7dWqfQ-09G7CJKyK) of reversing a linked list?

The time complexity is **O(n)** because each node must be visited once.

### 3\. Can you reverse a linked list recursively?

Yes, recursion is possible but may lead to [**stack overflow**](https://en.wikipedia.org/wiki/Stack_overflow) if the list is too long.

---

## Internal Links

* [**Learn more about Linked List Operations**](https://hojaleaks.com/introduction-to-linked-lists-and-types-of-linked-lists-data-structures-and-algorithms-day-3) to master insertion, deletion, and traversal.
    
* [**Arrays vs. Linked Lists**](https://hojaleaks.com/introduction-to-arrays-and-operations-data-structures-and-algorithms-day-2)**:** Which data structure should you use for different scenarios?
    

---

## Try It Yourself!

Reversing a linked list is a key skill in data structures, and mastering it will help you write more efficient code. Whether you choose an iterative or recursive approach, try implementing both for deeper understanding. **Test your code** with edge cases, such as empty lists or lists with only one node, to solidify your knowledge.

---

%[https://youtu.be/E1dnkjd3nAc?si=nNwG0ldAduL8jVLL]