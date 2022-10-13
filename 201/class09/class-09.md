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
