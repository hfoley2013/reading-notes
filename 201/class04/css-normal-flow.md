# CSS: Normal Flow

## Reading

* [CSS: Normal Flow](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow)

## Notes

### Normal Flow

* Normal Flow is the layout of elements on a webpage before CSS is applied
* A document easily readable in Normal Flow will be much easier to work with in CSS

### Default Layout of Elements

* **Block Level Elements**
  * By default, content fills the available inline space of the parent element containing it and grows along the block dimension to accommodate its content
* **Inline Elements**
  * By default, inline elements are only as large as their content
    * You can't set the `width` or `height` of inline elements, they just sit inside block-level elements
  * To control the size of an inline element, you need to set it to behave like a block-level element via `display: block;` or `display: inline-block;`
