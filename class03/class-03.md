# Class 3: Reading Notes & Assignment Summary

## Assignments

### Learn HTML

* **When should you use an `unordered list` in your HTML document?**
  * When the order of the items presented is immaterial to their understanding or usage
* **How do you change the `bullet style` of unordered list items?**
  * Change `type` as follows:
  
  <blockquote>
  <ul type="circle"><li>`circle`</li></ul><ul type="disc"><li>`disc`</li></ul><ul type="square"><li>`square`</li></ul>
  </blockquote>

* **When should you use an `ordered list` vs an `unordered list` in your HTML document?**
  * Ordered lists should be used when the sequence of the items in the lists matters
  * This could be a set of directions, a finishing order, or a hierarchy of attributes 
* **Describe two ways you can change the numbers on `list items` provided by an `ordered list`?**
  * Ordered lists can be displayed with the following markers by changing `type`:
    * `a` lowercase letters
    * `A` uppercase letters
    * `i` lowercase Roman numerals
    * `I` uppercase Roman numerals
    * `1` number (default)

### Learn CSS: The Box Model

* **Describe the CSS properties of `margin` and `padding` as characters in a story. What is their role in a story titled: “The Box Model”?**
  * `margin` is the whitespace between the box and other elements
  * `padding` is the whitespace inside the box between the `content` and the `border`
* **List and describe the four parts of an HTML elements box as referred to by the `box model.`**
  * **Content**
    * Area where your content is displayed
  * **Padding**
    * Whitespace around the content
  * **Border**
    * Wraps the content and padding
  * **Margin**
    * Whitespace between other elements

  ![CSS Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model/box-model.png)

### Learn JS: Arrays, Operators & Expressions, Conditionals, & Loops

* **What `data types` can you store inside of an `Array`?**
  * An array can take any data type and store it, including another array (*multidimensional array*)
* Is the `people` array a valid JavaScript array? If so, how can I access the values stored? If not, why?
  * Yes, the array is valid
  * You can access the values using `people[#][#]` to pick the array and item
    * Example
      * `people[1][0]`: Smith
      * `people[0][1]`: 32

  ``` js
  const people = [['pete', 32, 'librarian', null], ['Smith', 40, 'accountant', 'fishing:hiking:rock_climbing'], ['bill', null, 'artist', null]];
  ```

* **List *five* shorthand operators for assignment in javascript and describe what they do.**

| **Name** | **Shorthand operator** |	**Meaning** |
| --- | --- | --- |
| Assignment	| x = f()	| x = f() |
| Addition assignment	| x += f() | x = x + f() |
|Subtraction assignment |	x -= f()	| x = x - f() |
| Multiplication assignment |	x *= f() |	x = x * f() |
| Division assignment |	x /= f() |	x = x / f() |

* **Read the code below and evaluate the last `expression` and explain what the result would be and why.**
  * Prints: `10dog`
  * `a` is a `number` and converted to a `string` when concatenated with a `string`
  * `c` is a `boolean` value that is set to `false`, so the value is `0`
  * The expression is adding `a` + `c` together (10 + 0), and thus returning `10` as the value to concatenate with `dog`
    * If `c` were set to `true`, the output would change to `11dog`

  ``` js
  let a = 10;
  let b = 'dog';
  let c = false;

  // evaluate this
  (a + c) + b;
  ```

* **Describe a real world example of when a conditional statement should be used in a JavaScript program.**
  * An `if` statement can be use anytime a decision needs to be made by the program based on prior inputs or data
  * Example from Class Lab 02
    * In this sample code, JS evaluates a user's answer to a series of questions vs. an index of correct answers and returns a response of `Correct!` or `Incorrect!` based on if the answers match

    ``` js
        if (userAns == correctAns[i]) {
      console.log('correct');
      correctCount = correctCount + 1;
      console.log(correctCount);
      alert(`Correct! ${responseAlert[i]}`);
    } else{
      console.log('incorrect');
      alert(`Incorrect! ${responseAlert[i]}`);
    }
    ```

* **Give an example of when a `Loop` is useful in JavaScript.**
  * `Loops` are useful when you need to run the same code over and over again
  * Example: NASA Countdown

  ``` js
  let countDown = 10;

  for (let i = countDown; i >= 0; i--) {
    console.log(`Countdown: ${i}`);
  } console.log('Blast Off!');
  ```
