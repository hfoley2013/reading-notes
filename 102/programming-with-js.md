# Programming with JavaScript

[MDN Control Flow](https://developer.mozilla.org/en-US/docs/Glossary/Control_flow)
[JavaScript Functions](https://www.w3schools.com/js/js_functions.asp)
[JavaScript Operators](https://www.w3schools.com/js/js_operators.asp)
[Expressions & Operators - Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)
[Functions - Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)

## Control Flow

* ***Control flow*** is the order in which the computer executes statements in a script
* Code is run in order from the first line to the last line, unless the computer encounters a code structure that changes the flow, such as *conditionals* or *loops*
  * In the example below, if the user leaves the `field` empty, they will be prompted to enter the data; otherwise, the form will be submitted

``` js
if(isEmpty(field)) {
  promptUser();
} else {
  submitForm();
}
```

## JavaScript Functions

* Function is a block of code designed to perform a specific task
* A JS function is executed with something ***invokes*** it (*calls it*)
  * When an event occurs
  * When it is called from JavaScript code
  * Automatically, if self-invoked

### Why Functions?
  
  * Functions allow you to reuse code
    * Define the code once, and use it many times

### JS Function Syntax

* Defined with the `function` keyword, followed by a **name**, followed by parentheses `()`
* Code to be executed is contained within `{}`
* Parameters names are separated with commas `,`

``` js
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```

### Function Return

* When JS reaches a `return` statement, the function will stop executing
* If the function was invoked from a statement, JS will "return" to execute the code after the invoking statement
* Functions often compute a **return value** that is then "return" back to the "caller"

``` js
let x = myFunction(4, 3);   // Function is called, return value will end up in x

function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}
```
The result in *x* wil be:

``` js
12
```

## Global vs. Local Variables

## Global Variables

* Are declared outside of a function and are accessible to the entire code block

``` js
let carName = "Ford"
// code here CAN use carName

function myFunction() {
  return "I love my " + carName
// code here CAN use carName
}
// code here CAN use carName
```

## Local Variables

* Are declared within a code block and are only accessible by that piece of code

``` js
// code here can NOT use carName

function myFunction() {
  let carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```