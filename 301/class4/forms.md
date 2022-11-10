# React and Forms

## Readings

* [React Docs - Forms](https://reactjs.org/docs/forms.html)
* [The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)

## References

* [React Bootstrap - Forms](https://react-bootstrap.github.io/forms/overview/)
* [React Docs - conditional rendering](https://reactjs.org/docs/conditional-rendering.html)

## Questions

### React Docs - Forms

* **What is a ‘Controlled Component’?**
  * An element who's value is controlled by the React state
  * Updates via a handle function using `setState()`
* **Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why?**
  * You want to update the React state as the user inputs their responses so that they can see what inputs they have made
  * If you waited until the user submitted the form to update the React state, the user would not be able to see their responses until form submission
* **How do we target what the user is entering if we have an event handler on an input field?**
  * Use `event.target.name` within the handler function to create a variable that can be passed to `<input>`

### The Conditional (Ternary) Operator Explained

* **Why would we use a ternary operator?**
  * 
* **Rewrite the following statement using a ternary statement:**

  ```js
  if(x===y){
    console.log(true);
  } else {
    console.log(false);
  }
  ```

  ```js
  (x === y ? true : false);
  ```

## Notes

### Forms

* Controlled components
  * An element who's value is controlled by the React state
  * Updates via a handle function using `setState()`
  * Examples:
    * `<input>`: Allows user to input a value or upload a file type
    * `<textarea>`: Create an area to write in with content inside a `<value>` tag
    * `<select>`: Creates a dropdown list
* The React state should update as the user makes in the application, not after the form is submitted
  * If the state doesn't update until after submission, the user cannot see what inputs they have notes

### Ternary Operator

* Shorthand `if()` statement
* `?` functions like this:
  * Is the preceding condition `true`?
* Syntax

  ```js
  condition ? value if true : value if false
  ```
  
## In Class Notes

* [addNotes]
