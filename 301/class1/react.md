# Class 1: React

## Reading

* [Component Based Architecture](https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm)
* [What is Props and How to Use it in React](https://codefellows.github.io/code-301-guide/curriculum/class-01/DISCUSSION#:~:text=What%20is%20Props%20and%20How%20to%20Use%20it%20in%20React)

## References

* [React Tutorial through ‘Passing Data Through Props’](https://reactjs.org/tutorial/tutorial.html)
* [React Docs - Hello world](https://reactjs.org/docs/hello-world.html)
* [React Docs - Introducing JSX](https://reactjs.org/docs/introducing-jsx.html)
* [React Docs - Rendering elements](https://reactjs.org/docs/rendering-elements.html)
* [React Docs - Components and props](https://reactjs.org/docs/components-and-props.html)

## Notes

* For each `class` based component you must:
  * `import` React `from` 'react';
  * `class` `<fileName>` `extends` React.Component {}
  * `export` default `<fileName>`;
  * **NOTE:** `<fileName>` does *NOT* include the `.js` ending
* React likes to keep all components inside of **one component**
  * Can wrap all components inside a `<div>` to eliminate errors in VS Code
    * **NOTE:** This can create a series of unwanted `<div>`'s 
  * To avoid having extra or unwanted `<div>`'s, you can "fool" React by wrapping all components in empty tags `<>`:
    * `<>` `</>`
* React component names should start with an `Uppercase`, while html elements stay `lowercase`
