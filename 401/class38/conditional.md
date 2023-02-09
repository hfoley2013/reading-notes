# Conditional Rendering in React

## Reading

* [React - Conditional Rendering](https://reactjs.org/docs/conditional-rendering.html)
* [React - Lists & Keys](https://reactjs.org/docs/lists-and-keys.html)
* [React - Forms](https://reactjs.org/docs/forms.html)
* [React - Lifting State](https://reactjs.org/docs/lifting-state-up.html)
* [React - Composition vs Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
* [Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
* [React - Comprehensive Guide](https://tylermcginnis.com/reactjs-tutorial-a-comprehensive-guide-to-building-apps-with-react/)
* [Heroicons](https://heroicons.com/)

## Notes

### Inline IF with Logical && Operator

```jsx
function Mailbox(props) {
  const unreadMessages = props.unreadMessages;
  return (
    <div>
      <h1>Hello!</h1>
      {unreadMessages.length > 0 &&
        <h2>
          You have {unreadMessages.length} unread messages.
        </h2>
      }
    </div>
  );
}

const messages = ['React', 'Re: React', 'Re:Re: React'];

const root = ReactDOM.createRoot(document.getElementById('root')); 
root.render(<Mailbox unreadMessages={messages} />);
```

It works because in JavaScript, `true && expression` always evaluates to `expression`, and `false && expression` always evaluates to `false`.

Therefore, if the condition is `true`, the **element right after && will appear in the output**. 

If it is false, React will ignore and skip it.

NOTE: Returning a falsy expression will still **cause the element after && to be skipped** ***but*** will **return the falsy expression**. In the example below, <div>0</div> will be returned by the render method.

```jsx
render() {
  const count = 0;
  return (
    <div>
      {count && <h1>Messages: {count}</h1>}
    </div>
  );
}
```

### Inline If-Else with Conditional Operator

`condition ? true : false.`

```jsx
render() {
  const isLoggedIn = this.state.isLoggedIn;
  return (
    <div>
      The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.
    </div>
  );
}

// Also
render() {
  const isLoggedIn = this.state.isLoggedIn;
  return (
    <div>
      {isLoggedIn
        ? <LogoutButton onClick={this.handleLogoutClick} />
        : <LoginButton onClick={this.handleLoginClick} />
      }
    </div>
  );
}
```
