# In memory storage

## Readings

* [Understanding the JavaScript Call Stack](https://medium.freecodecamp.org/understanding-the-javascript-call-stack-861e41ae61d4)
* [JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)

## Questions

### Understanding the JavaScript Call Stack

* **What is a ‘call’?**
  * Invoking of a function
* **How many ‘calls’ can happen at once?**
  * One call can happen at a time
* **What does LIFO mean?**
  * Last In, First Out
  * Last function into the stack gets popped out first when the function returns
* **Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.**

  ```js
  function firstFunction(){
    console.log("Hello from firstFunction");
  }

  function secondFunction(){
    firstFunction();
    console.log("The end from secondFunction");
  }

  secondFunction();
  ```
  
  * `secondFunction` gets called first and put into the stack
  * It then call `firstFunction`, pushing it into the stack
  * `firstFunction` logs `Hello from firstFunction` and is popped off the stack
  * `secondFunction` the moves up in the stack, is executed and logs `The end from secondFunction` and pops off the stack, clearing the memory
* **What causes a Stack Overflow?**
  * A recursive function calls itself without an exit point
    * I.E. the function will continuously execute itself, never popping off the stack

### JavaScript error messages

* **What is a ‘reference error’?**
  * Reference does not exist, undefined, or undeclared
* **What is a ‘syntax error’?**
  * You have a typo
* **What is a ‘range error’?**
  * Length given during object manipulation is invalid
  * The length was too long, too short, or negative
* **What is a ‘type error’?**
  * The type of variable you are using is incompatible with the function being called
* **What is a breakpoint?**
  * Stops the execution of the code if specific conditions are met at that point
  * **NOTE:** Breakpoints can be conditional or unconditional (the code always stops)
* **What does the word ‘debugger’ do in your code?**
  * `debugger` adds a breakpoint to your code, allowing you to review the history of what has run up until that breakpoint

## Notes

* Call Stack
  * Used for function invocation (call)
  * Executes one function at a time in order from top to bottom
  * Last Function in is First Function Executed
* Summary
  1. It is single-threaded. Meaning it can only do one thing at a time.
  2. Code execution is synchronous.
  3. A function invocation creates a stack frame that occupies a temporary memory.
  4. It works as a LIFO — Last In, First Out data structure.
* Error Handling: `Try` `Catch`

  ```js
  (function testing(){
    function add(a, b) {
      try {
        var result = a + b
        return result.split('')
      } catch (error) {
        console.error('add went wrong ->', error)
        return [] // default value
      }
    }
    var stringResult = add("1", "2")
    var numberResult = add(1, 2)
  })();
  ```

  * `try{}` contains the code you want to execute
  * `catch{}` contains the code you want to execute if there is an error

## Warm-Up

* `require(express)` needs `''` around `express` => `require('express)`
* `username` needs `/`
* `req` & `res` not referenced; change to `request` & `response`
* `res.send(userInfo)`
* `const userInfo {}` has no object info inside

## Lab 10: Cache

```js
let cache = {
  variable-name: {
    data: <the data sent to the front end>
    timeStamp: <time we put data in the cache>}
}
```

* Within the API call function on the back end, create a key,value pair to send to the cache
  * `let key = searchedValue + 'Data';`
* Using the key created, add a property to the cache with the value of the response data we are sending to the front end
* Also create a conditional statement within the call function to evaluate 1.) is there a cache and 2.) is it recent enough

  ```js
  if (cache[key] && cache[timeStamp]) {
    //if data is cached && recent enough, return the cache data
  } else {
    //make a new request to the API
    //put data into cache
  }
  ```

  ```js
  cache[key] = {
    data: <data-variable>,
    timeStamp: Date.now()
  }
  ```
