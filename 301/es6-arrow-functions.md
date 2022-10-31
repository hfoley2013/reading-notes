# ES6 Arrow Functions

## References

* [ECMAScript 2015](https://www.ecma-international.org/ecma-262/6.0/)
* [MDC Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
* [caniuse.com](https://caniuse.com/#search=arrow%20functions)
* [Function Expressions](https://developer.mozilla.org/en-US/docs/web/JavaScript/Reference/Operators/function)
* [Function Declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)
* [JavaScript Arrow Functions by Wes Bos](https://wesbos.com/arrow-functions/)

## Tasks

* **Create a new repo in your GitHub account called `arrow-functions`. Clone the empty repo to your dev environment.**
* **Navigate to the `prework` folder in the root directory of the class repository. Then navigate into the arrow-functions folder.**
* **Copy the contents of the folder named `starter-code` into your newly-created repo. Make an initial commit with the unchanged starter code.**
* **Proceed to work on a well-named branch. As you work, remember to add, commit, and push regularly.**
* **The `app.js` file contains examples of function expressions, as you are accustomed to seeing. Work through steps 1-9, reading the notes and reviewing the refactored samples.**
* **For each of these steps, uncomment the console.log line. Open the `index.html` file in the browser and verify the correct output in the developer console.**
* **To complete step 10, refactor the function expressions one at a time. Uncomment the console.log line and use it to check that the output is the same after you have completed the refactoring process.**
* **To complete step 11, uncomment the two console.log lines and observe the output in the developer console in the browser. Answer the corresponding questions.**


## Notes

* Arrow functions are **compact** alternative to writing a traditional functions
  * This can reduce the amount of code you write, but they **CANNOT** be used in the following situations:
    1. Do not bind to `this`, `arguments`, or `super`
    2. Should not be used as *methods*
    3. Do not have access to `new.target` keyword
    4. Not suitable for `call`, `apply`, and `bind` methods
    5. Cannot be used as *constructors*
    6. Cannot use `yield` within its body

### Syntax

```js
// Traditional Anonymous Function
(function (a) {
  return a + 100;
});

// Arrow Function Break Down

// 1. Remove the word "function" and place arrow between the argument and opening body bracket
(a) => {
  return a + 100;
};

// 2. Remove the body braces and word "return" — the return is implied.
(a) => a + 100;

// 3. Remove the argument parentheses
a => a + 100;
```

* When `()` are required
  * **Multiple arguments**
  * **No arguments**

  ```js
    // Traditional Anonymous Function
  (function (a, b) {
    return a + b + 100;
  });

  // Arrow Function
  (a, b) => a + b + 100;

  const a = 4;
  const b = 2;

  // Traditional Anonymous Function (no arguments)
  (function() {
    return a + b + 100;
  });

  // Arrow Function (no arguments)
  () => a + b + 100;
  ```

* When `{}` and `return` are required
  * If the body of the function requires **additional lines** of processing

  ```js
    // Traditional Anonymous Function
  (function (a, b) {
    const chuck = 42;
    return a + b + chuck;
  });

  // Arrow Function
  (a, b) => {
    const chuck = 42;
    return a + b + chuck;
  };
  ```

  * Named functions
    * Treat arrow expression like a variable

    ```js
    // Traditional Function
    function bob(a) {
      return a + 100;
    }

    // Arrow Function
    const bob2 = (a) => a + 100;
    ```
