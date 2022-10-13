# Class 9: Reading Notes & Assignment Summary

## Assignments

### HTML Forms

* **Why are forms so important in web development?**
  * They are one of the primary ways for users to interact with a website or application
  * Forms allow you to capture and store user data
* **When designing a form, what are some key things to keep in mind when it comes to user experience**
  * Keep the form simple
    * The longer the form, the more likely users will not complete it or be confused by it
  * Label inputs clearly to avoid confusing the user
    * Use form validation to keep the user from entering the wrong information
  * Make the form easy to scan by using headers to divide information from the user into sections
* **List 5 form elements and explain their importance.****
  * `<form>` define that there will be a form on the webpage
  * `<label>` defines the label for each input
  * `<input>` creates input method to interact with the user
  * `<textarea>` creates an input area in which the user can input free text
  * `<button>` creates a button that executes a specific action with the form


### Introduction To JavaScript Events

* **How would you describe events to a non-technical friend?**
  * An event is when something happens in the browser
    * The user clicks a button or hovers over a certain element on the page
* **When using the addEventListener() method, what 2 arguments will you need to provide?**
  * You need to provide the **name of the event**, and a **function to handle the event**
* **Describe the event object. Why is the target within the event object useful?**
  * Parameter usually specified as `event`, `evt`, or `e`
  * Allows you to pass event handlers automatically and provides extra features and information, such as `keydown` and `KeyboardEvent`
* **What is the difference between event bubbling and event capturing?**
  * Modern browser run 3x phases when an event fires: capture, target, and bubbling
  * **Event Capture**
    * Browser checks to see if the element's outer-most ancestor (`<html>`) has a `click` event associated with it and runs it if it exists
    * Then the browser moves down to the next elements and checks, and repeats until it reaches the direct parent of the element that was clicked
  * **Event Bubbling**
    * The browser checks to see if the direct parent of the clicked element has a `click` event handler registered on it for the bubbling phase and runs if so
    * Bubbling the chains events together to "bubble up" from inside the first element outwards

## In Class Notes

### Code Review

* `display: flex` only works it applied to the *parent container*
  * This is only affect *direct children* within the parent container

### Events

* Events are **fired** or **raised** and **triggers** or **invokes** code
* Event types
  * `click`
  * `submit`
  * `onChange`
  * `hover`
  * `on page load`
  * `on mouse over`
  * `on key release`
* **Event Listener**
  * Code that is TRIGGERED when an event is FIRED
* **Bind**
  * Bind or tether an event listener to the event
* **Event Handler**
  * Code that runs in response to an event
* **Callback Function**
  * Any function that is passed into another function as an argument
* **Asynchronous Code**
  * Code that runs out of order
  * Might have to wait for something else to run before it can fire
* **Event Bubbling**
  * Event occurs inside a child element and propagates outward
    * Outside listening to inside elements
  * Allows you to put a single event listener on a container and respond to events occurring on child elements with in the container
* **Event Capturing**
  * The inverse of Event Bubbling
  * Child elements listening for events on the parent element
* **DOM 2 Level Event Handler is what we will use as eventListeners()**
  * DO THIS
    * `let element = document.getElementById('someId');`
    * `element.addEventListener`
    * addEventListener takes in 2 arguments:
      * An event as a *string* (e.g. `click'`)
      * A callback function to run

      ```js
      function greeting(name) {
        console.log(`Hello ${name}`);
      }

      function processUserInput(callBack) {
        let name = prompt('Please enter your name:');
        callback(name);
      }

      processUserInput(greeting);
      ```

  * *Do NOT use these older methods below*
    * In the HTML: `<article onClick="handleClick">` >> No JavaScript in the HTML
    * In the JavaScript: `element.onEvent = functionName` 
      * Example: `button(document.getElementById('button')).onSubmit = handleEvent;`

### Adding Event Listeners

* Summary Steps
  1. Window into the DOM
  2. Add eventListener
  3. Declare a function to be the event handler
* First step is to create a variable taken from the DOM
  * Ex: `let container = document.getElementById('container')`
* Second, add the eventListener() to the variable
  * Ex: `container.addEventListener('click', handleClick);`
    * This adds a `'click'` event listener that fires the function `handleClick` when the `container` element is clicked in the DOM
* Third, create teh callback function code block
  * Ex:
  
    ```js
    `function handleClick(event) {
      console.log('click happened');
      console.log('event');
    }`
    ```
  
  * `event` gets information passed to it by `addEventListener` when the listener is activated since `handleClick` is the call back function
    * `event` is an object that gets passed a series of `key: value` pairs related to the event

### Forms

* Created with `<form>`
* Link labels to inputs two ways:
  * The value of `for` in the `<label>` tag should match the id of the input it goes with
  * Make the `<input>` a child of the `<label>`

    ```html
    <label for="kittenName">Kitten Name</label>

    <label>Kitten Name
      <input type="text" name="kittenBreed">
    </label>
    ```

* `<fieldset>` is the equivalent of `<section>` within a table
  * `<legend>` is like a heading for elements within a `<fieldset>` of a table

### Steps for Working with Forms

* Summary Steps
  1. Window into the DOM
     * Use `querySelector` to create a variable to hold the `form` data

       ```js
       let form = document.querySelector('form');
       ```

  2. Add eventListener
     * Look for `'submit'` event
     * Create name for event handler

      ```js
      form.addEventListener('submit', handleSubmit);
      ```

  3. Declare an event handler to take in the form `'submit'` event
     * Will need to override defaults with 

    ```js
    let handleSubmit = function(event) {
      event.preventDefault();
      // nameKitten comes from the name attribute in HTML
      console.log(event.target.nameKitten.value);
    }
    ```
