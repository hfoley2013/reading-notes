# CSS: The Box Model

## Readings

* [The Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)

### The Box Model

#### Block & Inline Boxes

* There are two types of boxes in CSS:
  1. **Block boxes**
  2. **Inline boxes**
* The type refers to how the box behaves in terms of page flow and in relation to other boxes
* Displays
  * **Outer display type**
    * `block`
      * Box will break into a *new line*
      * `width` & `height` properties are respected
      * Padding, margin, and border *push* elements *away* from the box
      * Box will extend inline to fill the space in its container, usually 100% of space available unless otherwise specified
      * `<h1>` & `<p>` use `block` as their **default** outer display type
    * `inline`
      * Box will *not* break onto a new line
      * `width` & `height` will *not* apply
      * Vertical padding, margin, and borders will apply, but *not* cause other *inline* boxes to move away
      * Horizontal padding, margin, and borders will apply and *will* cause other *inline* boxes to move away
      * `<a>`, `<span>`, `<em>`, & `<strong>` use `inline` as their **default** outer display type
  * **Inner display type**
    * Determines how elements inside the box are laid out
  
#### [What is the CSS Box Model?](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)

* **Content**
  * Area where your content is displayed
* **Padding**
  * Whitespace around the content
* **Border**
  * Wraps the content and padding
* **Margin**
  * Whitespace between other elements

![CSS Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model/box-model.png)

#### Standard Box Model

* `height` and `width` attributes are applied to the *content box*
* `margin`, `padding`, and `border` will be added to the content box to give you the actual size of the box

``` css
.box {
  width: 350px;
  height: 150px;
  margin: 10px;
  padding: 25px;
  border: 5px solid black;
}
```

* The actual space of the box will be 410px wide (350 + 25 + 25 + 5 + 5) and 210px high (150 + 25 + 25 + 5 + 5)
![Standard Box](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model/standard-box-model.png)

#### Alternative Box Model

* `height` and `width` attributes will be applied to the *whole* box
* Activated with `box-sizing: border-box;`
![Alternative Box](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model/alternate-box-model.png)
