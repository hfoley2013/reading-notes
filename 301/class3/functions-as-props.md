# Passing Functions as Props

## Readings

* [React Docs - lists & keys](https://reactjs.org/docs/lists-and-keys.html)
* [The Spread Operator](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)
* [Video: How to Pass Functions Between Components](https://www.youtube.com/watch?v=c05OL7XbwXU)

## References

* [React Tutorial through ‘Declaring a Winner’](https://reactjs.org/tutorial/tutorial.html)
* [React Docs - Lifting State Up](https://reactjs.org/docs/lifting-state-up.html)

## Questions

### React Docs - lists and keys

* **What does .map() return?**
  * `.map()` creates a new array populated with the results of running a callback function over every item in the array
* **If I want to loop through an array and display each value in JSX, how do I do that in React?**
  * You would create a function that renders the values in the array as React elements
  
  ```jsx
  function renderNum() {
    const numbers = [1, 2, 3, 4, 5];
    const listItems = numbers.map((number) =>
      <li key={number.toString()}>
        {number}
      </li>
    );

    return (
      <ul>{listItems}</ul>
    );
  }
  ```

* **Each list item needs a unique ____.**
  * `key`
* **What is the purpose of a key?**
  * These keys help React identify which items have changed, are added, or are removed

### The Spread Operator

* **What is the spread operator?**
  * `...`
  * Passes values in an array to a function as separate arguments
* **List 4 things that the spread operator can do.**
  1. Copy Arrays
  2. Concatenate Arrays
  3. Pass separate arguments to `Math` function
  4. Add new values to an array
* **Give an example of using the spread operator to combine two arrays.**

  ```js
  let numArr1 = [1,2,3];
  let numArr2 = [4,5,6];

  let numArr = [...numArr1,...numArr2]
  ```

* **Give an example of using the spread operator to add a new item to an array.**

  ```js
  let names = ['tom', 'dick', 'harry'];
  let moreNames = [...names, 'jane', 'janet'];
  console.log(moreNames)//tom, dick, harry, jane, janet
  ```

* **Give an example of using the spread operator to combine two objects into one.**

  ```js
  let hello = ['hello', 'world'];
  let greet = ['what', 'a', 'beautiful', 'day'];
  let phrase = [...hello,...greet] //hello world what a beautiful day
  ```

### How to Pass Functions Between Components

* **In the video, what is the first step that the developer does to pass functions between components?**
  * You first need to define the function at the parent level
  * You can then reference that function in the child components using `this.props.<functionName>`
* **In your own words, what does the `increment` function do?**
  * Increments the state of the rendered component's `count` property by 1 each time the `Add` button is clicked by the user
* **How can you pass a method from a parent component into a child component?**
  * Use `this.props.<functionName>`
* **How does the child component invoke a method that was passed to it from a parent component?**
  * Use `this.props.<functionName>(this.props.<arg>)` to invoke the parent function using the corresponding parameter from the child component

## Notes

### Lists & Keys

* `.map()` creates a new array populated with the results of running a callback function over every item in the array
* Each list item in JSX requires a unique `key`
  * Can use a specific unique ID inherent to the item, or pass `index` to serve as the `key`
  * These keys help React identify which items have changed, are added, or are removed

### Spread Operator

* The spread operator is `...`
* It passes the values of an array into a function as *separate arguments**

### Passing Functions Between Components

* First define the function at the parent level
* The parent function can then be passed to the child component using `this.props.<functionName>`

## In Class Notes

### For lab
  
* set state `heart` in `App.js`
* create method to update heart in `App.js`
* pass `state: heart` to `Header.js` 
* pass the method to `HornedBeast.js` components
* The state can be passed to child using a constructor created above the `render()` function in `App.js`
* Pass the state to the `Header` component by adding `hearts={this.state.hearts}` to the `<Header>` component in `App.js`
* Next, in `Header.js`, reference the state via `this.props.hearts` where ever you want to render the value of `hearts`
* The `addHearts` method needs to be added to the `<Header>` component in `App.js` as well
  * Invoke the function in the `<Header>` with `{this.addHearts}`
  
  ```jsx
  addHearts = () => {
    this.setState({
      hearts: this.state.hearts + '<heartImg>'
    });
  };
  ```
  
  * Modals
    * Need to add `<Modal/>` to `App.js`
      * Remember to import the `Modal` from Bootstrap into `App.js`
    * Will need two handle functions to open & close the modal
      
      ```jsx
      handleCloseModal = () => {
        this.setState({
          isModalShown: false
        });
      };

      handleOpenModal= () => {
        this.setState({
          isModalShown: true
        });
      };
      ```
      
    * `<Modal>` will take a `show` and `onHide` property that holds these functions:
      * `<Modal show={this.state.isModalShown} onHide={this.handleCloseModal}>`
