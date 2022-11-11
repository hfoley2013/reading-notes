# Putting it All Together: Thinking in React

## Readings

* [Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
* [Higher Order Functions](https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK)

## Questions

### Thinking in React

* **What is the `single responsibility principle` and how does it apply to components?**
  * Each component should only do one thing
  * Components will be responsible for a specific function within the application
* **What does it mean to build a ‘static’ version of your application?**
  * Build out the UI using components, but don't add any interactivity to the site
  * You will reuse components using `props` and ignore using `state` in this phase
* **Once you have a static application, what do you need to add?**
  * `state` so that you can track user interactions with the application
* **What are the three questions you can ask to determine if something is state?**
  1. **Is it passed in from a parent via props? If so, it probably isn’t state.**
  2. **Does it remain unchanged over time? If so, it probably isn’t state.**
  3. **Can you compute it based on any other state or props in your component? If so, it isn’t state.**
* **How can you identify where state needs to live?**
  * Identify *every* component that **renders something** based on that state.
  * Find a **common owner component** (a single component above all the components that need the state in the hierarchy).
  * Either the **common owner** or another component higher up in the hierarchy **should own the state.**
  * If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

### Higher-Order Functions

* **What is a “higher-order function”?**
  * Higher-order functions are functions that take other functions as arguments or change other functions by acting on them
* **Explore the `greaterThan` function as defined in the reading. In your own words, what is line 2 of this function doing?**
  * The second line of the function is allow the entire function to be passed as an argument `m` and compares that against the parameter `n`
* **Explain how either `map` or `reduce` operates, with regards to higher-order functions.**
  * `map` is a higher-order function that mutates an existing array by calling  a function and running that function over each value in the array

## Notes

### React Docs - Thinking in React

* `Single Responsibility Principle`
  * Each component should *only* **do one thing**
* Build a static site
  * Build out your components to reuse other components using `props` and render the UI, but do not add in interactivity yet
  * This means that you will **not** be making use of `state`
    * `state` is reserved for tracking user inputs (i.e. interactivity)
* Questions to Ask to Determine is Something Should be in `state`
  1. **Is it passed in from a parent via props? If so, it probably isn’t state.**
  2. **Does it remain unchanged over time? If so, it probably isn’t state.**
  3. **Can you compute it based on any other state or props in your component? If so, it isn’t state.**
* Determining where your `state` should live
  * Identify *every* component that **renders something** based on that state.
  * Find a **common owner component** (a single component above all the components that need the state in the hierarchy).
  * Either the **common owner** or another component higher up in the hierarchy **should own the state.**
  * If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

## In-Class Notes

* [addNotes]
