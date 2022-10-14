# Troubleshooting JavaScript 

## Reading

* [What Went Wrong? Troubleshooting JavaScript.](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_went_wrong)

## Notes

### Types of Errors

* **Logic Error**
  * Code runs successfully, but gives the wrong result
  * These are hard to fix since there is no error code to direct you to the source of the problem
* **Syntax Error**
  * Spelling error which breaks your code
  * The console will print out an Error code and that returns what type of error it is, as well as what line of code and what character on that line the error begins

### Common Errors

* **SyntaxError: missing ; before statement**
  * Forgot the `;` at the end of a line
* **SyntaxError: missing ) after argument list**
  * Missed closing `)` at the end of a function/method call
* **SyntaxError: missing : after property id**
  * Incorrectly formed JS object
    * Misplaced `{}` or `()` in object
* **SyntaxError: missing } after function body**
  * Missed closing `}`
* **SyntaxError: expected expression, got 'string' or SyntaxError: unterminated string literal**
  * Left off a string value's opening or closing quote mark
