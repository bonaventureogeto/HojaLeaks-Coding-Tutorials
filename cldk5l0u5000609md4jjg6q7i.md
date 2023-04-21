---
title: "HTML & CSS Fundamentals: A Comprehensive Guide"
seoTitle: "HTML & CSS Fundamentals: A Comprehensive Guide"
datePublished: Tue Jan 31 2023 11:25:18 GMT+0000 (Coordinated Universal Time)
cuid: cldk5l0u5000609md4jjg6q7i
slug: html-css-fundamentals-a-comprehensive-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1675164163842/423e9571-4102-495b-b68c-83170c88aef0.png
tags: programming-blogs, css, web-development, html5, beginners

---

## Introduction

HTML (Hypertext Markup Language) and CSS (Cascading Style Sheets) are the building blocks of the web. HTML is used to structure the content of a webpage, while CSS is used to style and format it. This tutorial will give an in-depth understanding of HTML and CSS and how they work together to create a website.

## HTML

HTML consists of tags that describe the structure and content of a webpage. The tags are surrounded by angle brackets (&lt; &gt;) and come in pairs to define an element. Here is a list of some common HTML tags:

1. `<html>`: Defines the root of an HTML document
    
2. `<head>`: Contains information about the document, such as the title and metadata
    
3. `<title>`: Specifies the title of the document, which is displayed in the browser's title bar
    
4. `<body>`: Contains the main content of the document
    
5. `<h1> - <h6>`: Defines headings, with `<h1>` being the largest and most important
    
6. `<p>`: Defines a paragraph
    
7. `<a>`: Defines a hyperlink
    
8. `<img>`: Embeds an image in the document
    
9. `<ul>`: Defines an unordered list
    
10. `<li>`: Defines a list item
    

Example of a basic HTML document:

```xml
<!DOCTYPE html>
<html>
  <head>
    <title>My First HTML Page</title>
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first HTML page.</p>
  </body>
</html>
```

## CSS

CSS is used to style and format the content of an HTML document. CSS can be added to an HTML document in three ways:

1. Inline CSS: Style is added directly to an HTML element using the `style` attribute
    
2. Internal CSS: Style is added to the `<head>` section of an HTML document using the `<style>` tag
    
3. External CSS: Style is added to a separate .css file, which is linked to the HTML document using the `<link>` tag
    

CSS uses a selector to select the HTML element to be styled, and a declaration block to specify the styles to be applied. The declaration block consists of a property and a value, separated by a colon (:) and surrounded by curly brackets ({ }).

Example of a CSS declaration block:

```css
p {
  color: blue;
  font-size: 16px;
}
```

In the example above, the selector `p` selects all `<p>` elements and the declaration block sets the text color to blue and the font size to 16 pixels.

### CSS Box Model

The CSS box model is a concept that defines the size and layout of an HTML element on a webpage. It consists of four parts:

1. Content: The content area, where the text and images are displayed
    
2. Padding: The space between the content and the border
    
3. Border: A line that surrounds the padding and content
    
4. Margin: The space outside the border
    

The size of an element can be controlled by setting its \`width and height`properties, as well as its`padding`,` border`, and` margin\` properties. The total size of an element can be calculated as:

```css
total size = width + padding + border + margin
```

Example of CSS Box Model:

```css
div {
  width: 300px;
  height: 200px;
  padding: 10px;
  border: 5px solid black;
  margin: 20px;
}
```

In the example above, the total size of the `div` element will be `340px` in width and `240px` in height.

### CSS Layout

CSS provides several layout methods for controlling the position and flow of elements on a webpage. Some of the most common layout methods are:

1. Normal Flow: The default layout method, where elements are arranged in the order they appear in the HTML document
    
2. Float: Allows elements to float to the left or right of the parent container
    
3. Flexbox: Provides a flexible layout for elements, allowing them to grow or shrink as needed
    
4. Grid: Provides a grid-based layout for elements, allowing them to be arranged in rows and columns
    

Each of these layout methods has its own advantages and disadvantages, and choosing the right method depends on the requirements of the webpage.

Example of CSS Flexbox Layout:

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.item {
  width: 200px;
  height: 100px;
  background-color: lightblue;
  margin: 10px;
}
```

In the example above, the `container` class uses the `display: flex` property to enable the flexbox layout, and the `justify-content` and `align-items` properties to center the items vertically and horizontally.

### Conclusion

HTML and CSS are essential skills for web development, and this tutorial has provided an in-depth understanding of how they work together to create a webpage. There is much more to learn about HTML and CSS, including advanced topics like responsive design, accessibility, and animation. However, with the basics covered, you can now start building your own websites and explore these advanced topics further.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!