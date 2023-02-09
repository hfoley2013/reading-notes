# React Context

## Readings

* [React Context for Beginners](https://www.freecodecamp.org/news/react-context-for-beginners/)
* [Video: Why I’m using Next.js in 2020](https://www.youtube.com/watch?v=rtgbaKBhdkk)
* [Video: Learn useContext In 13 Minutes](https://www.youtube.com/watch?v=5LrDIWkK_Bc)
* [Next.js Examples](https://github.com/vercel/next.js/tree/canary/examples)

## Notes

### What is React Context?

React context allows us to pass down and use (consume) data in whatever component we need in our React app without using props.

### When should I use React Context?

React context is great when you are passing data that can be used in any component in your application.

These types of data include:

* Theme data (like dark or light mode)
* User data (the currently authenticated user)
* Location-specific data (like user language or locale)

Data should be placed on React context that **does not need to be updated often**.

### Why use React Context?

Avoid ***props drilling***: when you pass props down multiple levels to a nested component, through components that don't need it.

### How do I use React Context?

There are four steps to using React context:

1. Create context using the createContext method.
2. Take your created context and wrap the context provider around your component tree.
3. Put any value you like on your context provider using the value prop.
4. Read that value within any component by using the context consumer.

### What is the useContext hook?

A way to consume context with the `useContext` hook.

Instead of using `render props`, we can pass the entire context object to `React.useContext()` to consume context at the top of our component.

```jsx
import React from 'react';

export const UserContext = React.createContext();

export default function App() {
  return (
    <UserContext.Provider value="Reed">
      <User />
    </UserContext.Provider>
  )
}

function User() {
  const value = React.useContext(UserContext);  
    
  return <h1>{value}</h1>;
}
```

### More on Context

#### What is React Context?

React Context is a feature in React that allows you to share data throughout your application without having to pass props down through multiple levels of components. It provides a way to pass data through the component tree without having to pass props down manually at every level.

Context is created by using the `React.createContext()` method, which returns an object with a Provider and Consumer component. The Provider component is used to provide the data to the components within its scope, while the Consumer component is used to access the data.

```jsx
const MyContext = React.createContext();

function App() {
  const data = {
    message: "Hello World!"
  };

  return (
    <MyContext.Provider value={data}>
      <MyComponent />
    </MyContext.Provider>
  );
}

function MyComponent() {
  return (
    <MyContext.Consumer>
      {data => <div>{data.message}</div>}
    </MyContext.Consumer>
  );
}
```

In this example, the data object is passed to the MyContext.Provider component as the value prop. The MyComponent component can then access this data by using the `MyContext.Consumer` component.

#### Using Context

Using context in React involves the following steps:

1. **Create a context:** You can create a context using the React.createContext() method, which returns an object with a Provider and Consumer component.

```jsx
const MyContext = React.createContext();
```

2. **Provide the data:** The Provider component is used to provide the data to the components within its scope. You can pass the data to the Provider component as the value prop.

```jsx
function App() {
  const data = {
    message: "Hello World!"
  };

  return (
    <MyContext.Provider value={data}>
      <MyComponent />
    </MyContext.Provider>
  );
}
```

3. **Access the data:** The Consumer component is used to access the data. You can access the data by using the Consumer component and providing a render prop function that returns a React component.

```jsx
function MyComponent() {
  return (
    <MyContext.Consumer>
      {data => <div>{data.message}</div>}
    </MyContext.Consumer>
  );
}
```

NOTE: The *Provider* component must be a **parent** component of the *Consumer* component for the Consumer component to access the data. The Provider component can be nested multiple levels deep within the component tree, but it should be placed at the highest level possible to minimize the number of unnecessary re-renders.

React Context solves the problem of having to pass props down through multiple levels of components, which can quickly become cumbersome and difficult to manage, especially in larger applications.

#### Why use Context?

Some of the main problems that Context solves include:

1. **Boilerplate code:** When props are passed down multiple levels, it can result in a lot of boilerplate code. Context eliminates the need to pass props down through multiple components, making your code more concise and maintainable.
2. **Reusability:** Components that require access to the same data are often not easily reusable because they require props to be passed down from their parent components. With Context, these components can access the data directly, making them more reusable.
3. **Performance:** When props are passed down through multiple levels, each component in the chain triggers a re-render, which can negatively impact performance, especially in larger applications. With Context, components only re-render when the data they need changes, which can result in better performance.
4. **State management:** In larger applications, managing state can become complex, especially when state needs to be shared between components that are not directly related. Context makes it easier to share state between components by providing a centralized location for the data.

By solving these problems, Context can make your React code more **organized**, **maintainable**, and **performant**.
