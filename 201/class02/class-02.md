# Class 2: Reading Notes & Assignment Summary

## Assignments

### Introduction to HTML

* **Why is it important to use semantic elements in our HTML?**
  * So that we can easily determine the function of an element in our document.
    * Is it part of the main content? Is it a header to attract attention?
    * Is the element a standalone article or a section of a website that cannot be used out of context?
    * These semantic elements can also be identified and used for quickly formatting them in CSS
* **How many levels of headings are there in HTML?**
  * There are *6 levels* of headings in HTML
* **What are some uses for the `<sup>` and `<sub>` elements?**
  * `<sub>` can be used to generate subscripts for text
  * `<sup>` generates superscripts that can be used for adding references/footnotes into a document
* **When using the `<abbr>` element, what attribute must be added to provide the full expansion of the term?**
  * You need to add `<title>` into the element to have it show the full text of the abbreviation
  
  ``` html
  <p>
    We use <abbr title="Hypertext Markup Language">HTML</abbr> to structure our web documents.
  </p>
  ```

  <blockquote>
    <p>
     We use <abbr title="Hypertext Markup Language">HTML</abbr> to structure our web documents.
    </p>
  </blockquote>

### Learn CSS

* **What are ways we can apply CSS to our HTML?**
  * External Stylesheets
  * Internal Stylesheets
  * Inline Styles
* **Why should we avoid using inline styles?**
  * Inline styles override any external or internal stylesheets
  * Additionally, inline styles make your HTML code harder to read
* **Review the block of code below and answer the following questions:**
  * What is representing the selector?
    * `h2`
  * Which components are the CSS declarations?
    * `color: black;`
    * `padding: 5px;`
  * Which components are considered properties?
    * `color`
    * `padding`

``` css
h2 {
  color: black;
  padding: 5px;
}
```

### Learn JavaScript

#### JavaScript Basics

* **What data type is a sequence of text enclosed in single quote marks?**
  * `String`
* **List 4 types of JavaScript operators.**
  * `+` Addition
  * `-` Subtraction
  * `*` Multiplication
  * `/` Division
* **Describe a real world problem you could solve with a `function`.**
  * You could write a function to convert temperature from Fahrenheit to Celsius

  ``` js
  function convertTemp(fTemp) {
    return cTemp = (fTemp - 32) * (5/9);
    console.log(cTemp);
    alert(`${fTemp} F is ${cTemp} C`)
  }
  ```

#### Making Decisions in Your Code - Conditionals

* **An if statement checks a __ and if it evaluates to ___, then the code block will execute.**
  * An if statement checks a *conditional statement* and if it evaluates to *true*, then the code block will execute.
* **What is the use of an else if?**
  * `else if` allows you to chain together a series of conditional statements to evaluate and run code blocks based on those conditions
* **List 3 different types of comparison operators.**
  * `==` Equals
  * `===` Strictly Equals
  * `>=` Greater than or equal to
* **What is the difference between the logical operator `&&` and `||`?**
  * `&&` is an `AND` statement
    * It requires that *both* conditions be satisfied in order to execute the code
  * `||` is an `OR` statement
    * It requires that *one or the other* conditions be satisfied in order to execute the code

## Reading Notes Summary

### [HTML Text Fundamentals](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)

### [HTML Advanced Text Formatting](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting)

### [How CSS is Structured](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured)

### [JavaScript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)

### [Making Decisions in Your Code - Conditionals](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)
