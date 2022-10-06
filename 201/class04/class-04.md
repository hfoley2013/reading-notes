# Class 4: Reading Notes & Assignment Summary

## Assignments

### Learn HTML

* **To create a basic link, we wrap text or other content inside what element?**
  * `<a>` tags
* **The href attribute contains what information?**
  * The link URL
* **What are some ways we can ensure links on our pages are accessible to all readers?**
  * Use clear link wording
    * Search engines use link text to index target files, so include keywords in your link text to effectively describe to the search engine what is being linked to
    * Make links standout so visual readers can scan and find them easily
    * Don't use the URL as part of the text, they are ugly
    * Keep the text short and descriptive of where the link goes

### CSS Layout

* **What is meant by “normal flow”?**
  * Normal Flow is the layout of elements on a webpage before CSS is applied
* **What are a few differences between `block-level` and `inline` elements?**
  * **Block Level Elements**
  * By default, content fills the available inline space of the parent element containing it and grows along the block dimension to accommodate its content
* **Inline Elements**
  * By default, inline elements are only as large as their content
    * You can't set the `width` or `height` of inline elements, they just sit inside block-level elements
  * To control the size of an inline element, you need to set it to behave like a block-level element via `display: block;` or `display: inline-block;`
* **___ positioning is the default for every html element.**
  * Static positioning is the default for every html element
* **Name a few advantages to using absolute positioning on an element.**
  * Removes it completely from the normal flow and places it on its own unique layer
  * Allows you to **isolate UI features that don't interfere with the layout of other elements**
* **What is a key difference between fixed positioning and absolute positioning?**
  * Fixed positioning locks an element in place within the viewport and it does not move
    * Text, images, etc. will move around the element and the element will interact with other elements on the webpage
  * Absolute positioning places the element on its own unique plane and it will no longer interact with elements on the webpage

### JavaScript

* **Describe the difference between a function declaration and a function invocation.**
  * Declare = make a function
  * Invoke = run the function
* **What is the difference between a parameter and an argument?**
  * They are the same thing
  * They are values needed by the function inside the function parenthesis in order for the function to run properly

### Miscellaneous

* **Pick 2 benefits to pair programming and reflect on how these benefits could help you on your coding journey.**
  * Greater Efficiency
    * The more time you can spend coding, the more you are going to learn
    * Having a partner allows you to divide up work when you encounter issues with your code and keep moving forward
    * Additionally, your partner may immediately know the solution to the problem and can keep the process moving forward
  * Engaged Collaboration
    * I do admit that it is easy to get distracted when programming alone
    * Having another person working on the same project with me would likely keep me on task to a higher degree and result in earlier completion times
