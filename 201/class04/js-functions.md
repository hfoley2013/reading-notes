# JavaScript Functions

## Reading

* [Functions - Reusable Blocks of Code](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions)

## Notes

### Functions

* Allow you to store pieces of code for reuse throughout your program
* Hallmark sign is `()` at the end of a word
* Must be *declared* with `function`
* Must be *invoked* to run with `()`
* Can take arguments/parameters inside the `()`, or may have optional parameters

### Anonymous Functions

* Functions with no name
* Typically take another function as an argument
* `keydown` event & `logKey` example
  * Instead of defining a separate `logKey` function to record keystrokes, you can just pass the function directly into another function like so:

  ```js
  // Declaring a Separate Function
  function logKey(event) {
  console.log(`You pressed "${event.key}".`);
  }

  textBox.addEventListener('keydown', logKey);

  // Passing the function directly with Anonymous Function
  textBox.addEventListener('keydown', function(event) {
  console.log(`You pressed "${event.key}".`);
  });
  ```

  * You can also use **Fat Arrow Notation** to create the function without having to write `function`

  ```js
  textBox.addEventListener('keydown', (event) => {
  console.log(`You pressed "${event.key}".`);
  });
  ```
