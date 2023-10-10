---
title: "Introduction To The JavaScript DOM"
seoTitle: "Introduction To The JavaScript DOM 101"
datePublished: Tue Oct 10 2023 11:42:15 GMT+0000 (Coordinated Universal Time)
cuid: clnk95hkn000209id1wci1ig0
slug: introduction-to-the-javascript-dom
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/wUbNvDTsOIc/upload/a17bcf0ca9419fe78ee5d735172f707c.jpeg
tags: software-development, javascript, web-development, dom-manipulation

---

## **What is the DOM?**

The DOM (Document Object Model) is an object-oriented representation of the HTML and XML documents. It represents the structure of a web page as a tree-like structure of objects, with each object representing an element in the HTML document.

JavaScript can be used to manipulate the DOM, allowing you to add, remove, and modify elements on a web page dynamically.

## **Accessing DOM elements**

The first step in working with the DOM is accessing the elements you want to manipulate. There are several ways to do this:

### **By ID**

The most common way to access a DOM element is by its ID attribute. You can use the `document.getElementById()` method to get the element with a specific ID:

```javascript
const myElement = document.getElementById('my-id');
```

### **By tag name**

You can also access elements by their tag name using the `document.getElementsByTagName()` method. This method returns an array-like collection of elements with the given tag name:

```javascript
const myElements = document.getElementsByTagName('p');
```

### **By class name**

You can also access elements by their class name using the `document.getElementsByClassName()` method. This method returns an array-like collection of elements with the given class name:

```javascript
const myElements = document.getElementsByClassName('my-class');
```

### **By CSS selector**

Finally, you can access elements using CSS selectors with the `document.querySelector()` and `document.querySelectorAll()` methods. These methods allow you to select elements using any valid CSS selector:

```javascript
const myElement = document.querySelector('#my-id');
const myElements = document.querySelectorAll('.my-class');
```

## Accessing and Modifying DOM Elements:

To access and modify a DOM element, we need to first obtain a reference to it using one of the methods mentioned above. Once we have the reference, we can use the various properties and methods provided by the element object to modify its attributes and content.

For example, to change the text content of a paragraph element with the ID "myPara", we can use the following code:

```javascript
var para = document.getElementById("myPara");
para.textContent = "New Text Content";
```

Similarly, to change the background color of a div element with the class name "myDiv", we can use the following code:

```javascript
var divs = document.getElementsByClassName("myDiv");
for (var i = 0; i < divs.length; i++) {
  divs[i].style.backgroundColor = "red";
}
```

Creating and Deleting DOM Nodes:

In addition to modifying existing DOM elements, we can also create new elements and add them to the document, or remove existing elements from the document.

To create a new element, we can use the `document.createElement(tagName)` method. This method returns a new element object that we can then modify and add to the document using the various DOM manipulation methods.

For example, to create a new paragraph element with some text content and add it to the document, we can use the following code:

```javascript
var para = document.createElement("p");
para.textContent = "New Paragraph Text";
document.body.appendChild(para);
```

To delete an existing element from the document, we can use the `element.parentNode.removeChild(element)` method. This method removes the specified element from its parent node and returns a reference to the removed element.

## **Manipulating DOM elements**

Once you have accessed a DOM element, you can manipulate it in a number of ways.

### **Changing text content**

You can change the text content of an element using the `textContent` property:

```javascript
myElement.textContent = 'New text content';
```

### **Changing HTML content**

You can change the HTML content of an element using the `innerHTML` property:

```javascript
myElement.innerHTML = '<strong>New HTML content</strong>';
```

### **Changing attributes**

You can change the attributes of an element using the `setAttribute()` method:

```javascript
myElement.setAttribute('class', 'new-class');
```

You can also access and modify attributes directly using the element's properties:

```javascript
myElement.className = 'new-class';
```