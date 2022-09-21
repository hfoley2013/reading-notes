# JavaScript Basics

[JS Intro](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[Introduction to JavaScript - basic output](https://code-maven.com/introduction-to-javascript)
[JavaScript input with prompt and confirm](https://code-maven.com/javascript-input-with-prompt-and-confirm)
[Variable](https://www.w3schools.com/js/js_variables.asp)
[How Computers Work - Playlist](https://www.youtube.com/playlist?list=PLzdnOPI1iJNcsRwJhvksEo1tJqjIqWbN-)

## JS Intro

JavaScript (JS) is a lightweight, interpreted, or [just-in-time](https://en.wikipedia.org/wiki/Just-in-time_compilation) compiled programming language with [first-class functions](https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function). While it is most well-known as the scripting language for Web pages, many non-browser environments also use it, such as Node.js, Apache CouchDB and Adobe Acrobat. JavaScript is a [prototype-based](https://developer.mozilla.org/en-US/docs/Glossary/Prototype-based_programming), multi-paradigm, [single-threaded](https://developer.mozilla.org/en-US/docs/Glossary/Thread), [dynamic](https://developer.mozilla.org/en-US/docs/Glossary/Dynamic_typing) language, supporting object-oriented, imperative, and declarative (e.g. functional programming) styles. 

[Read more about JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/About_JavaScript)

## Basic Use

* JS can be **embedded** or **included**
  * Embed = JS put directly into HTML file
    * `<script>` tag is used
  * Include = Line placed into HTML file that references the JS file

### Basic Inputs & Outputs

| Code | Does |
| --- | --- |
| `alert()` | Creates a pop-up with the alert text inside |
| `document.write()` | Changes the content on the page to what is inside the `document.write()` function |
| `console.log()` | Prints the contents of the `console.log()` call into the console for us to read |
| `prompt()` | Shows a pop-up window asking for a user's input |
| `confirm()` | Provides a `Yes` or `No` confirmation to the user; typically paired with an `IF` / `ELSE` statement

## Variables

### What are Variables?

* Variables are **containers for storing data values**
* There are *four* ways to declare a variable:
  * `var`
  * `let`
  * `const`
  * Nothing
* Variables require an ***identifier***
  * This is the name follow the declaration
    * Example:
      * `let person = "John"`
        * `person` is the identifier
* JS treats the following as letters, and thus as valid variable names:
  * Any letter
  * `$`
  * `_`

``` js
var x = 5;
var y = 6;
var z = x + y;
console.log(z) >> 11
```

### When to Use `const`?

* As a general rule, always declare variables with `const`
* `const` cannot be accidentally modified later in the program
  * If you do try and modify a `const`, you will get an error message
* If a variable can change, use `let`

``` js
const price1 = 5;
const price2 = 6;
let total = price1 + price2;
console.log(total) >> 11
```