# React: States & Props

## Readings

* [React Lifecycle](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)
* [Video: React State vs. Props](https://www.youtube.com/watch?v=IYvD9oBCuJI)

## References

* [React Docs - State and Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)
* [React Docs - handling events](https://reactjs.org/docs/handling-events.html)
* [React Tutorial through ‘Developer Tools’](https://reactjs.org/tutorial/tutorial.html)
* [React Bootstrap Documentation](https://react-bootstrap.github.io/)
* [Boootstrap Cheatsheet](https://getbootstrap.com/docs/5.0/examples/cheatsheet/)
* [Bootstrap Shuffle - a class “sandbox”](https://bootstrapshuffle.com/classes)
* [Netlify](https://www.netlify.com/)

## Questions

### React Lifecycle

* **Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?**
  * `Render` occurs before `componentDidMount` in the order of operations
* **What is the very first thing to happen in the lifecycle of React?**
  * A `constructor` is created
* **Put the following things in the order that they happen: `componentDidMount`, `render`, `constructor`, `componentWillUnmount`, `React Updates`**
  * Order of operations:
    1. `constructor`
    2. `static`
    3. `getDerivedStateFromProps`
    4. `render`
    5. `componentDidMount`
    6. `UNSAFE_componentWillMount`
* **What does `componentDidMount` do?**
  * Allows us to execute React code when the component is already in the DOM

### React State vs Props

* **What types of things can you pass in the props?**
* **What is the big difference between props and state?**
* **When do we re-render our application?**
* **What are some examples of things that we could store in state?**

## Notes

### React: Component Lifecycle Events

![Component Lifecycle](https://miro.medium.com/max/720/0*0saPKFiTUk6W3FYp)

* **Mounting**
  * Component gets created and inserted into the DOM
  * Order of operations:
    1. Constructor
    2. `static`
    3. `getDerivedStateFromProps`
    4. `render`
    5. `componentDidMount`
    6. `UNSAFE_componentWillMount`
* **Updating**
  * Occurs anytime a component is updated or changes state
  * Order of operations:
    1. `static getDerivedStateFromProps`
    2. `shouldComponentUpdate`
    3. `render`
    4. `getSnapshotBeforeUpdate`
    5. `componentDidUpdate`
    6. `UNSAFE_componentWillUpdate`
    7. `UNSAFE_component WillReceiveProps`

* **Unmounting**
  * Component is removed from the DOM
  * Uses `componentWillUnmount`
