# CSS: Positioning

## Reading

* [CSS: Positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)

## Notes

### Static Positioning

* `static` is the default positioning for every HTML element
* This means that the element *will display in its **normal** position* in the document flow

### Relative Positioning

* `position: relative;`
* Allows you to utilize the `top`, `bottom`, `left`, and `right` properties to place the element
  * These elements ***push from*** the direction specified
    * `top: 30px;` means "Push the element 30px from the *top*"

### Absolute Positioning

* `position: absolute;`
* Removes the element from the normal flow and sits it on its own layer separate from everything else
* Allows you to **isolate UI features that don't interfere with the layout of other elements**
  * Examples: pop-ups, control menus, UI features that can be dragged and dropped anywhere on the page

### Fixed Positioning

* `position: fixed;`
* Locks an element in a position relative to the visible portion of the viewport
* Text will move around these elements and the element will remain fixed in teh viewport at all times

### Sticky Positioning

* `position: sticky;`
* Hybrid between `relative` and `fixed`
* Allows elements to act like it's relatively positioned until it's scrolled to a certain threshold, after which it becomes fixed
  * Example: Scrolling index where headers stick to the top of a page as you scroll
