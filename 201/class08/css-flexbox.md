# CSS Flexbox

## Readings

* [Learn CSS - Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)
* [CSS Layout - Flexbox](https://web.dev/learn/css/flexbox/)

## Notes

### What is Flexbox?

* A one-dimensional layout method for arranging items in row or columns
* Items *flex* (expand) to fill additional space or shrink to fit into smaller spaces
* Set using `display: flex;` in CSS

### Why Flexbox?

* Simplifies vertical and horizontal alignment of a block of content inside its parent
* Makes all children of a container take up an equal amount of the available width/height
  * I.E. Auto-sizes the children and evenly distributes them within the space available inside the parent
* Makes all columns in a multi-column layout adopt the same height, even if they have a different amount of content

### Simple Example

* Assume you have an HTML file that has the following structure:

  ``` html
  <header>Sample flexbox example</header>
  <section>
    <article>First article</article>
    <article>Second article</article>
    <article>Third article</article>
  </section>
  ```

  ![Flexbox Example](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/bih741v.png)

* We now select the elements that we want displayed as flexible boxes
  * In this case, we want the `<artilce>` elements to display as flexboxes, creating 3x equal sized boxes evenly distributed within the parent element `<section>`

  ``` css
  section {
    display: flex;
  }
  ```

  ![Display Flex](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example2.png)

### The Flex Model

* Flex elements are laid out on two axes:
  * **Main axis**
    * Runs the direction of distribution
      * This property can be changed with `flex-direction`

        ```css
        flex-direction: column;
        ```

  * **Cross axis**
    * Runs perpendicular to the main axis

  ![Flex Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flex_terms.png)

### Wrapping

* You can allow text to wrap inside your flex items using `flex-wap: wrap;`
* You can set the width of your boxes flexibility with `flex: unitOfMeasure;`

### Flex-Flow Shorthand

```css
flex-direction: row;
flex-wrap: warp;

/*becomes*/
flex-flow: row warp;
```

## Flex Sizing

* Can create dynamic sizing using the `flex` property
* `flex` is a **unitless** value that dictates **how much space** an element will take up along the **main axis** *relative* to other elements in the space
* For example:
  * 3x elements with `flex: 1` will each take 1/3rd of space available
  * But, if 1x element was set to `flex: 2`, that element would appear twice as large as the other elements (see below: Third article)

  ![Flex Sizing](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example1.png)
* ***NOTE: Use flex shorthand to prevent extra long code***
  * `flex` can specify `flex-grow`, `flex-shrink`, and `flex-basis`

### Suggestion for Navigation Buttons in Header Menu

```css
div {
  display: flex;
  align-items: center;
  justify-content: space-around;
}
```
