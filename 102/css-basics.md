# CSS

Articles

* [What is CSS?](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/What_is_CSS)
* [How to Add CSS](https://www.w3schools.com/css/css_howto.asp)
* [CSS Color Properties](https://www.w3schools.com/cssref/pr_text_color.asp)
* [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
* [CSS Tools](https://meyerweb.com/eric/tools/css/reset/)

## What is CSS?

* Cascading Style Sheets
* Allows you to format your webpages with color, borders, various fonts styles & sizes, etc.
* CSS is broken down into ***[modules](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)*** that contain all the relevant information for styling a specific property in a specified way
  * For example, if you want to reference the properties & values that format background and borders, you can visit the [Backgrounds and Borders](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders) module

## CSS Syntax

* CSS is rules-based
* You define the rules that will apply to specific groups of styles that will be applied to particular elements or groups of elements on a webpage
* Rules open with a ***selector***, such as `h1`, to specify which HTML element that will be styled
  * In this case, the style will apply to `<h1>` elements
* The styles to be applied to the selected element are contained within `{}`
* Inside the `{}` are ***declarations***, which take the form of a **property** and **value** pairs

``` CSS
h1 {
  color: red;
  font-size: 5em;
}

p {
  color: black;
}
```

## [Adding CSS to a Webpage](https://www.w3schools.com/css/css_howto.asp)

* There are three ways to insert CSS:
  * External CSS
  * Internal CSS
  * Inline CSS
* Styles will cascade in the following order:
  * Inline
  * External & internal style sheets (in the `<head>` section)
  * Browser default

### External CSS

* CSS code is written in a separate `.css` file
* This file is then **linked** to your HTML document with the `<link>` element within the `<head>` section

``` HTML
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

The external `.css` file will look like the following:

``` CSS
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
```

### Internal CSS

* Internal styles can be used if one single HTML page has a unique style
* The internal style is marked with the `<style>` element, inside of the head section

``` HTML
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

### Inline CSS

* An inline style may be used to apply a unique style to for a single element
* The `style` attribute is added within the HTML element
  * `style` may contain ***any*** CSS property

``` HTML
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```