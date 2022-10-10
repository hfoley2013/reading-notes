# Class 6: Reading Notes & Assignment Summary

## Assignments

### JavaScript Objects Basics

* **How would you describe an object to a non-technical friend you grew up with?**
  * An object is just a bunch of related data or things with similar functionality
* **What are some advantages to creating object literals?**
  * Taking a series of related data and sending it to a server inside a single object literal is more efficient than sending a series of individual items to a server separately
* How do objects differ from arrays?
  * Objects are a set of key,value pairs that define a single variable
    * For example: An object `person` may be made up of `height`, `weight`, `gender`, `age`, `eye color`
  * Arrays are a running list of items that make up a single variable
    * For example: `eye color` = `[blue, green, brown, black]`
* Give an example for when you would need to use bracket notation to access an object’s property instead of dot notation.
  * You can use bracket notation if an object's property name is held in a variable
  * In this case, the name cannot be accessed directly using dot notation, and therefore you will need to access the value using bracket notation
* Evaluate the code below. What does the term `this` refer to and what is the advantage to using `this`?
  * `This` refers to `dog`
  * `This` allows you to use the same method definition for every object that you create
  * In the code below, we could make another object `dog2` and use the same method to get the dog's name and age in human years without needing to change the code

``` js
const dog = {
  name: 'Spot',
  age: 2,
  color: 'white with black spots',
  humanAge: function (){
    console.log(`${this.name} is ${this.age*7} in human years`);
  }
}
```

### Introduction to the DOM

* What is the DOM?
  * Document Object Model is the programming interface for web documents
  * It turns the webpage into a series of nodes and objects that can be interacted with via a coding language (JavaScript, in our case)
  * It is constructed from multiple APIs that work together:
    * Core DOM defines the entities describing an y document and the objects within it
    * HTML DOM API adds support for representing HTML documents to the core DOM
    * SVG API adds support for representing SVG documents
* Briefly describe the relationship between the DOM and JavaScript.
  * Code is *written* in JavaScript that *uses* DOM to access the document and its elements
  * DOM provides the references necessary for JavaScript to target specific elements and respond to specific events on the web page
  * JavaScript access the DOM via `document` and `window` objects

### In Class Notes

* [addNotes]
