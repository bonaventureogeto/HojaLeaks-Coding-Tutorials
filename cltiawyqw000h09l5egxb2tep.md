---
title: "4 CSS Styles for Customizing List Appearance"
seoTitle: "4 CSS Styles for Customizing List Appearance"
datePublished: Fri Mar 08 2024 06:54:19 GMT+0000 (Coordinated Universal Time)
cuid: cltiawyqw000h09l5egxb2tep
slug: 4-css-styles-for-customizing-list-appearance
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/npxXWgQ33ZQ/upload/734c08ecd288ce3f578f7ea7c8d54589.jpeg
tags: css3, css, html5, frontend-development

---

CSS provides various properties to style lists in HTML, allowing you to customize the appearance of both ordered (numbered) and unordered (bulleted) lists. Here are some key CSS properties for styling lists, along with examples:

### 1\. `list-style-type`

This property changes the list item marker type.

* **For unordered lists:**
    
    * `disc` (default): a solid circle
        
    * `circle`: a hollow circle
        
    * `square`: a solid square
        
    * `none`: no marker
        

```css
ul.square-list {
  list-style-type: square;
}
```

* **For ordered lists:**
    
    * `decimal` (default): numbers (1, 2, 3, ...)
        
    * `lower-alpha`: lowercase letters (a, b, c, ...)
        
    * `upper-alpha`: uppercase letters (A, B, C, ...)
        
    * `lower-roman`: lowercase Roman numerals (i, ii, iii, ...)
        
    * `upper-roman`: uppercase Roman numerals (I, II, III, ...)
        
    * `none`: no marker
        

```css
ol.roman-list {
  list-style-type: upper-roman;
}
```

### 2\. `list-style-position`

This property specifies whether the list item markers appear inside or outside the content flow.

* `inside`: Markers are part of the text block and may disrupt text alignment.
    
* `outside` (default): Markers are outside the text block, which maintains text alignment.
    

```css
ul.inside-markers {
  list-style-position: inside;
}
```

### 3\. `list-style-image`

This property replaces the list item marker with an image.

```css
ul.image-list {
  list-style-image: url('path/to/your/image.png');
}
```

### 4\. Combining Properties

You can combine the above properties in a shorthand `list-style` property:

```css
ul.custom-list {
  list-style: square inside url('path/to/your/image.png');
}
```

This sets the list to have square markers (which is overridden by the image if the URL is valid), positions markers inside the content flow, and attempts to use the specified image as the marker.

### Example

Here's how you might apply these styles in HTML:

```html
<!-- Unordered List with Square Markers -->
<ul class="square-list">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<!-- Ordered List with Upper Roman Numerals -->
<ol class="roman-list">
  <li>First</li>
  <li>Second</li>
  <li>Third</li>
</ol>

<!-- Unordered List with Custom Image Markers -->
<ul class="image-list">
  <li>Apple</li>
  <li>Banana</li>
  <li>Cherry</li>
</ul>
```

Remember to adjust the `class` attribute of your list tags (`<ul>` or `<ol>`) to match the CSS class names you've defined.