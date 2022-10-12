# Class 8: Reading Notes & Assignment Summary

## Assignments

### Learn CSS - Flexbox

* **Flexbox is designed for one-dimensional content. Explain what this means.**
  * Content that displays in one direction across the page
  * Flexbox will layout a group of items in the direction specified
* **Explain the difference between the main axis and cross axis.**
  * Main axis is the axis across which the items will flex (expand)
  * The cross axis runs perpendicular to the main axis
* **How can using certain properties of flexbox negatively impact accessibility?**
  * Flexbox only changes the visual display of content on the webpage, not the structure of the HTML document
  * Screen-readers read the HTML document
  * Reversing or changing the order of the visual display away from the structure of the HTML document may result in confusion

### CSS Layout - Flexbox

* **What are some advantages of using flexbox over float?**
  * Keeps the items within the normal flow and positioned within their parent elements
  * Allows child elements to automatically distribute themselves within a parent element and take on the same height property
  * Simplifies the lines of code needed to create visually appealing displays and allows objects to remain within the normal flow and respond to additional elements added to the parent container
* **How does this topic connect with your long term goals?**
  * Another tool for the toolbelt
  * My goals is to create DRY code that is easily auditable with built in flexibility to respond dynamically to changes in HTML content as my webpage is updated
  * Flexbox provides a powerful structure to accomplish this goal

## In Class Notes

* `flex` should be applied to the **container (parent element)**, *not* the items themselves
* Default `flex-direction` is `row`
  * Can switch using `column`: will stack item on top of each other in a column
* `justify-content` aligns the flex items within the container
* Place holder link
  * https://place-hold.it/300x375/ddd
    * Link above is a grey 300x375 px box. Can change pixel layout and color code to make any box.
* Link Google Fonts with `src` attribute within the tag for the headers for Salmon Cookies
* Can use `lorem` within HTML to generate placeholder text directly
* To keep all content centered within the display window, use the below:

  ```css
  main {
    margin: auto;
  }
  ```
  
* `overflow: auto;` will create a scroll bar
