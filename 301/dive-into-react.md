# Dive Into React

## Watch

* [A High Level Overview of React](https://www.youtube.com/watch?v=FRjlF74_EZk)

## Questions

* **What is React?**
  * Agnostic user interface Library
    * Agnostic = does not care where your final UI will be displayed
  * Used to make anything that the user interfaces with in the browser
* **What is a component?**
  * A small part of the code that builds the UI when working with React
* **What is the dataflow of React?**
  * One-way data flow, not two-way binding
* **How do we make a React element a DOM element?**
  * You have to pass the element through React DOM to make it a DOM element
  * Creating `react.elements` results in native JavaScript *objects* before being run through React DOM
* **React is a User Interface ______.**
  * Library
* **Which direction does data flow in React?**
  * One-way
  * Helps reduce number of break points in your data
  * React components pass down data from their parent components
* **Every component manages its own ____.**
  * Component state
  * Each parent component can pass down its state to its child components
