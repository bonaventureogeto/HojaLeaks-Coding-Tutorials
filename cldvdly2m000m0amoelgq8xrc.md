---
title: "A Complete HTML & CSS Tutorial"
seoTitle: "A Complete HTML & CSS Tutorial"
datePublished: Wed Feb 08 2023 07:55:26 GMT+0000 (Coordinated Universal Time)
cuid: cldvdly2m000m0amoelgq8xrc
slug: a-complete-html-css-tutorial
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/SYTO3xs06fU/upload/0bdc2cfd010430d570efd1b2febb6d8c.jpeg
tags: programming-blogs, css, web-development, html5, wemakedevs

---

## I. Introduction to HTML

### A. What is HTML?

* HTML stands for HyperText Markup Language, it is a language used for creating and structuring web content.
    

### B. HTML Document Structure

* An HTML document consists of two main parts: head and body.
    
    * The head contains meta-information about the document and the title of the page, which is displayed in the browser's title bar.
        
    * The body contains the main content of the page, such as headings, paragraphs, images, and links.
        

### C. Basic HTML tags:

1. **Headings**: There are six levels of headings, from h1 to h6. h1 is the most important, and h6 is the least.
    

* Example: `<h1>This is a heading</h1>`
    

1. **Paragraphs**: A paragraph is represented by the `<p>` tag.
    

* Example: `<p>This is a paragraph.</p>`
    

1. **Lists**: There are two types of lists in HTML: unordered and ordered. An unordered list is represented by the `<ul>` tag and each list item is represented by the `<li>` tag. An ordered list is represented by the `<ol>` tag.
    

* Example of an unordered list:
    

```css
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

* Example of an ordered list:
    
* ```css
    <ol>
      <li>First item</li>
      <li>Second item</li>
      <li>Third item</li>
    </ol>
    ```
    
* **Links**: A link is represented by the `<a>` tag. The href attribute specifies the destination of the link.
    

* Example: `<a href="`[`https://www.example.com">Visit`](https://www.example.com">Visit) `my website</a>`
    

1. **Images:** An image is represented by the `<img>` tag. The src attribute specifies the source of the image and the alt attribute provides alternative text for the image.
    

* Example: `<img src="my-image.jpg" alt="My Image">`
    

### D. HTML Attributes

* HTML elements can have attributes, which provide additional information about the element.
    
* Some common attributes include:
    
    * id: Specifies a unique id for the element.
        
    * class: Specifies a class for the element.
        
    * style: Specifies styles for the element.
        
    * src: Specifies the source of an image or a resource.
        
    * href: Specifies the URL for a link.
        

### E. HTML Forms

* HTML forms are used for user input, such as submitting a search query, creating a user account, or making a purchase.
    
* A form is represented by the `<form>` tag and each form control, such as text fields, radio buttons, and checkboxes, are represented by different HTML elements.
    
* The action attribute of the form specifies where the form data will be sent when the form is submitted. The method attribute specifies the HTTP method used to send the form data.
    

### F. HTML Tables

* HTML tables are used to display data in a tabular format.
    
* A table is represented by the `<table>` tag, each row is represented by the `<tr>` tag, and each cell is represented by the `<td>` tag.
    
* The `<th>` tag is used to define header cells in a table.
    

### G. HTML Semantic Elements

* HTML5 introduced semantic elements, which provide more meaning to the content and structure of a web page.
    
* Some common semantic elements include:
    
    * `<header>`: Represents the header of a document or section.
        
    * `<nav>`: Represents a section of a page that contains navigation links.
        
    * `<main>`: Represents the main content of a document.
        
    * `<article>`: Represents a self-contained composition in a document, such as a blog post or a news story.
        
    * `<section>`: Represents a standalone section of a document, such as a chapter or a tabbed content area.
        
    * `<aside>`: Represents a section of a page that contains content that is tangentially related to the main content.
        
    * `<footer>`: Represents the footer of a document or section.
        

### Simple HTML Document Structure

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML Document</title>
  </head>
  <body>
    <h1>Welcome to my HTML Document</h1>
    <p>This is a simple paragraph.</p>
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ul>
    <a href="https://www.example.com">Visit my website</a>
    <img src="my-image.jpg" alt="My Image">
  </body>
</html>
```

## II. CSS Introduction

### A. What is CSS?

* CSS stands for Cascading Style Sheets and is used for styling and laying out web pages.
    
* CSS works in conjunction with HTML to create visually appealing and user-friendly websites.
    
* CSS allows you to control the layout, colors, fonts, and other design elements of your website, separate from the content (HTML).
    

### B. CSS Selectors

* CSS selectors are used to select HTML elements that you want to style.
    
* There are several types of selectors, including:
    
    1. Element Selectors: Select elements based on the HTML tag name. Example: `p` selector will select all `<p>` elements.
        
    2. Class Selectors: Select elements based on a class attribute. Example: `.my-class` selector will select all elements with class `my-class`.
        
    3. ID Selectors: Select elements based on an id attribute. Example: `#my-id` selector will select the element with id `my-id`.
        
    4. Attribute Selectors: Select elements based on an attribute and its value. Example: `a[href="`[`https://www.example.com`](https://www.example.com)`"]` selector will select all `<a>` elements with a `href` attribute equal to [`https://www.example.com`](https://www.example.com).
        
    5. Pseudo-class Selectors: Select elements based on a special state. Example: `a:hover` selector will select an `<a>` element when the mouse is hovering over it.
        

### C. CSS Properties

* CSS properties are used to control the visual presentation of HTML elements.
    
* There are several types of properties, including:
    
    1. Text Properties: Control the text appearance, such as font size, font color, etc.
        
    2. Box Properties: Control the box model, such as width, height, padding, margin, etc.
        
    3. Background Properties: Control the background appearance, such as background color, background image, etc.
        
    4. Border Properties: Control the border appearance, such as border size, border color, etc.
        
    5. Layout Properties: Control the layout and position of elements, such as display, float, position, etc.
        

### D. CSS Box Model

* The CSS box model refers to the layout and dimensions of HTML elements.
    
* Each HTML element is considered a rectangular box that has content, padding, borders, and margins.
    
* The width and height of an element are determined by the content, but can be affected by padding, borders, and margins.
    

### CSS Box Model Example:

```css
.my-element {
  width: 300px;
  height: 200px;
  padding: 20px;
  border: 10px solid blue;
  margin: 10px;
}
```

In this example, the `.my-element` selector has a width of 300px, a height of 200px, 20px of padding, a 10px solid blue border, and a 10px margin. The total width and height of the element will be affected by these values.

### E. CSS Inheritance

* CSS inheritance is a mechanism where properties are passed from parent elements to child elements.
    
* Child elements inherit the styles of their parent elements by default.
    
* You can override inherited styles by applying styles directly to the child elements.
    

### CSS Inheritance Example:

```css
<style>
  body {
    font-size: 20px;
    color: green;
  }

  .my-element {
    font-size: 30px;
  }
</style>

<body>
  <p>This is a paragraph.</p>
  <div class="my-element">
    <p>This is a paragraph inside a div.</p>
  </div>
</body>
```

In this example, the body has a font size of 20px and a color green. The child element `.my-element` has a font size of 30px, which overrides the font size inherited from the body. The color green is still inherited by the child element.

### **F. CSS Specificity**

* CSS specificity refers to the priority of styles applied to an element.
    
* When multiple styles are applied to an element, the style with the highest specificity wins and is applied to the element.
    
* Specificity is determined by the type, class, and id selectors used.
    

### CSS Specificity Example:

```css
<style>
  p {
    color: blue;
  }

  .my-element {
    color: green;
  }

  #my-id {
    color: red;
  }
</style>

<body>
  <p class="my-element" id="my-id">This is a paragraph.</p>
</body>
```

In this example, the `p` selector has the color blue, the `.my-element` selector has the color green, and the `#my-id` selector has the color red. The `#my-id` selector has the highest specificity, so the color of the paragraph will be red.

These are the basic concepts of CSS introduction. You can continue to learn and explore more about CSS.

## III. HTML & CSS Together

### Complete HTML & CSS Document

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      .container {
        width: 80%;
        margin: 0 auto;
      }

      h1 {
        color: blue;
        text-align: center;
      }

      p {
        font-size: 16px;
        line-height: 1.5;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>Welcome to my HTML & CSS Document</h1>
      <p>This is a simple paragraph with styles applied.</p>
    </div>
  </body>
</html>
```

### A. Linking CSS to HTML

To link CSS to an HTML document, you can include the CSS styles within the `<head>` section of the HTML document using a `<style>` tag. Alternatively, you can link an external CSS file to the HTML document using the `<link>` tag. The advantage of using an external CSS file is that the same styles can be reused across multiple HTML pages, making the maintenance of the styles much easier.

### Linking an External CSS File to an HTML Document:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <link rel="stylesheet" type="text/css" href="styles.css">
  </head>
  <body>
    <!-- Your HTML content here -->
  </body>
</html>
```

### B. CSS Classes & IDs

CSS classes and IDs are used to target specific elements in the HTML document and apply styles to them. The difference between classes and IDs is that a class can be applied to multiple elements in the HTML document, while an ID can only be used once in a document.

### Using CSS Classes:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      .highlight {
        background-color: yellow;
      }
    </style>
  </head>
  <body>
    <p class="highlight">This is a highlighted paragraph.</p>
    <p class="highlight">This is another highlighted paragraph.</p>
  </body>
</html>
```

### Using CSS IDs:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      #header {
        background-color: blue;
        color: white;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <header id="header">This is the header of the page.</header>
  </body>
</html>
```

### C. CSS Inheritance & Specificity

CSS inheritance allows styles to be passed down from a parent element to its child elements. For example, if you set the font-size of a parent element, all of its child elements will inherit that font-size unless explicitly overridden.

CSS specificity determines which style rules take precedence when multiple styles are applied to the same element. A more specific selector will take precedence over a less specific selector.

### CSS Inheritance:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      body {
        font-size: 16px;
      }

      .highlight {
        background-color: yellow;
      }
    </style>
  </head>
  <body>
    <p class="highlight">This is a highlighted paragraph with an inherited font-size of 16px.</p>
  </body>
</html>
```

### CSS Specificity:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      /* Less specific selector */
      p {
        color: green;
      }

      /* More specific selector */
      .highlight {
        color: yellow;
      }
    </style>
  </head>
  <body>
    <p class="highlight">This paragraph will be yellow, as the .highlight selector is more specific than the p selector.</p>
  </body>
</html>
```

### D. CSS Box Model & Layout

The CSS box model refers to the way that every HTML element is treated as a rectangular box, with content, padding, borders, and margins. The layout of a page can be controlled using the CSS box model properties, such as width, height, padding, borders, and margins.

### CSS Box Model:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      .box {
        width: 300px;
        height: 200px;
        padding: 20px;
        border: 2px solid black;
        margin: 30px;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <p>This is a box with content, padding, a border, and a margin.</p>
    </div>
  </body>
</html>
```

In addition to the CSS box model, there are various layout techniques that can be used to control the position of elements on a page, such as floating elements, using the `display` property, and using CSS grids and flexbox.

### Using Floating Elements:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      .left {
        float: left;
        width: 200px;
        height: 200px;
        background-color: lightblue;
      }

      .right {
        float: right;
        width: 200px;
        height: 200px;
        background-color: lightgreen;
      }
    </style>
  </head>
  <body>
    <div class="left"></div>
    <div class="right"></div>
  </body>
</html>
```

Using the `display` Property

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      .container {
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 200px;
      }

      .box {
        width: 100px;
        height: 100px;
        background-color: lightblue;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>
  </body>
</html>
```

### Using CSS Grids:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My HTML & CSS Document</title>
    <style>
      .grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, 1fr);
        grid-gap: 10px;
        height: 200px;
      }

      .box {
        background-color: lightblue;
      }
    </style>
  </head>
  <body>
    <div class="grid">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>
  </body>
</html>
```

With these techniques, you can control the layout of your HTML elements on a page and create visually appealing and functional designs.

## IV. Responsive Web Design with CSS

### A. Introduction to Media Queries

* Media Queries are a CSS technique used to change the style and layout of a website depending on the device or viewport size.
    
* It allows you to apply different styles based on different conditions, such as screen size, device orientation, and screen resolution.
    
* The basic syntax of a media query is as follows:
    

```css
@media screen and (min-width: 700px) {
  /* styles here */
}
```

* In this example, the styles inside the media query will only be applied when the viewport is 700 pixels or wider.
    
* Media queries can be used in conjunction with CSS styles to create a responsive design that adapts to the device or viewport size.
    

### B. Flexbox & Grid Layout

* Flexbox is a layout mode in CSS that allows you to align and distribute space among elements in a container, regardless of their size.
    
* It provides a flexible way to handle elements that don't have a fixed size, and also makes it easier to create responsive designs.
    
* Here's an example of how to use flexbox:
    

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

* In this example, the `.container` class is set to `display: flex` to make it a flex container.
    
* The `justify-content` property centers the elements horizontally within the container.
    
* The `align-items` property centers the elements vertically within the container.
    
* Grid Layout, on the other hand, provides a two-dimensional grid-based layout system for elements within the container.
    
* It provides a more structured way to handle elements and is often used to create complex designs that require precise alignment and spacing.
    
* Here's an example of how to use a grid layout:
    

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 16px;
}
```

* In this example, the `.container` class is set to `display: grid` to make it a grid container.
    
* The `grid-template-columns` property defines the number and size of columns in the grid. In this case, the grid has 3 columns, each with a width of 1 fractional unit.
    
* The `grid-gap` property sets the gap between each cell in the grid.
    

### Responsive Web Design

Here is a code snippet that demonstrates how to create a responsive design using media queries and flexbox:

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

@media screen and (min-width: 700px) {
  .container {
    flex-direction: row;
  }
}
```

* In this example, the `.container` class is set to `display: flex` to make it a flex container.
    
* The `justify-content` and `align-items` properties center the elements horizontally and vertically within the container.
    
* The media query checks the viewport size and applies a different style when the viewport is 700 pixels or wider. In this case, it sets the `flex-direction` property to `row` to change the direction of the elements within the container.
    

Here is another example of using Media Queries and Flexbox to create a responsive design:

```css
@media (max-width: 768px) {
  .container {
    width: 90%;
  }

  h1 {
    font-size: 20px;
  }
}

.container {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
}
```

In this example, the media query will target devices with a maximum width of 768px and adjust the styles of the .container class and the h1 heading. The .container class uses the Flexbox layout mode, setting the display property to flex and using other Flexbox properties to control the alignment and spacing of its child elements.

This code demonstrates how to create a responsive design that adapts to different screen sizes, providing a better user experience for users on different devices. With this code, the elements within the container will be centered on small screens and displayed in a row on larger screens.

It's important to note that the principles of responsive web design go beyond just using media queries and layout modes. Creating a responsive design also involves considering things like font sizes, images, and overall layout to ensure that your website looks and functions well on a variety of devices.

## V. Final Thoughts

### A. What to Learn Next

1. JavaScript: JavaScript is a scripting language that can be used to add interactivity and dynamic elements to web pages. Learning JavaScript will enable you to create more dynamic and interactive web pages.
    
2. Bootstrap: Bootstrap is a popular framework for creating responsive and mobile-friendly web pages. It offers pre-made CSS and JavaScript components, making it easier to create a consistent and professional-looking website.
    
3. Web Accessibility: Web accessibility is the practice of making web pages usable for people with disabilities. Learning about accessibility will help you create web pages that are usable for a wider range of people.
    

### B. Resources for Continued Learning

1. W3Schools: A comprehensive website that offers tutorials and reference materials for HTML, CSS, and JavaScript.
    
2. FreeCodeCamp: A non-profit organization that offers a comprehensive curriculum for learning web development. It includes interactive coding challenges and projects to help you apply what you learn.
    
3. Udemy: A platform that offers paid and free courses on web development, including HTML, CSS, and JavaScript.
    
4. MDN Web Docs: The official documentation website for the web, including detailed guides and reference materials for HTML, CSS, and JavaScript.
    

### C. Q&A

This is an opportunity for you to ask any questions you may have about the material covered in this workshop. You can also ask in the comments section, I'll be glad to answer them all.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy coding!