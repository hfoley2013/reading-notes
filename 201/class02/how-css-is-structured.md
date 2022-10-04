# How CSS is Structured

## Reading

* [How CSS is Structured](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured)

### Applying CSS to HTML

* CSS can be applied to HTML via *external* stylesheets, *internal* stylesheets, or *inline styles*
* External Stylesheets
  * Need to be **linked** to the document via the `<link>` element
    * `<link rel="stylesheet" href="styles.css" />`
* Internal Stylesheet
  * Designated in the `<head>` section of the document with the `<style>` element tag

``` html
<!DOCTYPE html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8" />
    <title>My CSS experiment</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }

      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>
```

  * Inline Styles
    * These declarations only affect *one* HTML element and will *override* any internal or external stylesheets
  
### Selectors

* Targets HTML to apply styles to content
* Selectors are the HTML elements or class designations to be targets by CSS

``` css
h1
a:link
.manythings
#onething
*
.box p
.box p:first-child
h1, h2, .intro
```

### Properties and Values

* Properties
  * Human-readable identifiers that indicate which stylistic feature you want to modify
* Values
  * How the property will be styled
* Example
  * `color` is the property and `blue` is the value

  ``` css
  h1 {
    color: blue;
  }
  ```
### Functions

* CSS can do simple mathematical functions
* `calc()`
* `rotate()`

### Shorthands

* Some properties set several values in a single line

``` css
/* In 4-value shorthands like padding and margin, the values are applied
   in the order top, right, bottom, left (clockwise from the top). There are also other
   shorthand types, for example 2-value shorthands, which set padding/margin
   for top/bottom, then left/right */
padding: 10px 15px 15px 5px;

  /* the above is equivalent to these four lines of code */
padding-top: 10px;
padding-right: 15px;
padding-bottom: 15px;
padding-left: 5px;
```
