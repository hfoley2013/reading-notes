# Making Decisions in your Code - Conditionals

## Reading

* [Making Decision in Your Code - Conditionals](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)

### if...else

``` js
if (condition) {
  /* code to run if condition is true */
} else {
  /* run some other code instead */
}
```

* `if()` designates the `if` function
* The statement evaluates the conditional statement for `true` or `false`
* If `true`, the code executes
* If `false`, the `else` code executes

### else if

* Provides a chain of extra conditional statements to evaluate for `true` and `false` conditions

``` js
if (condition) {
  /* code to run if condition is true */
} else if (another condition) {
  /* code to run if condition is true */
} //exit if statement and run code below
```

### Switch Statements

* Used when if...else statements would be extremely cumbersome
* Allow you to define multiple cases and run code based on the `case`

``` js
switch (expression) {
  case choice1:
    run this code
    break;

  case choice2:
    run this code instead
    break;

  // include as many cases as you like

  default:
    actually, just run this code
}
```
