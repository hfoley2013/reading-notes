# Functional Programming

## Readings

* [Functional Programming Concepts](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)
* [VIDEO: Node JS Tutorial for Beginners #6 - Modules and require()](https://www.youtube.com/watch?v=xHLd36QoS4k)

## Questions

### Functional Programming Concepts

* **What is functional programming?**
  * A style of programming that treats computation as pure mathematical functions
  * Does not change states or mutable data
  * Results will always be the same because the parameters are defined locally, not a mutable global object
* **What is a pure function and how do we know if something is a pure function?**
  * A function is "pure" if it always returns the same result given teh same arguments and doesn't create any observable side effects
* **What are the benefits of a pure function?**
  * Code is easier to test
  * Does not change the state of an existing data source so you will always have access to the original data
* **What is immutability?**
  * The thing cannot be changed or altered
* **What is Referential transparency?**
  * `pure functions + immutable data = referential transparency`
  * Function returns the same result for the same input

### Modules and require()

* **What is a module?**
  * Logical clumps of codes with similar, related, or specific functionality
* **What does the word ‘require’ do?**
  * Allows you to use a function in another file
* **How do we bring another module into the file the we are working in?**
  * Use `require('./<file-name>')` to bring in the file
  * Will need to declare a variable to handle the imported function
    * `let variable = require('./<filename>);`
* **What do we have to do to make a module available?**
  * Within the module, you will need to `export` the function
  * `module.exports = <function-name>;`
  * This allows the function to be exported from the module and imported into another module for use

## Notes

* TODO

## In Class Notes

* TODO
