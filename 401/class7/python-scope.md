# Python Scope

## Readings

* [Python Scope](https://realpython.com/python-scope-legb-rule/)
* [VIDEO: Don’t be CONFUSED by BIG O notation anymore!](https://www.youtube.com/watch?v=5Uqawfl0VHQ)

## Review

* [Rolling Dice Examples](https://artofproblemsolving.com/wiki/index.php/Basic_Programming_With_Python#Program_Example_1_3)


## Notes

### Python Scope & the LEGB Rule: Resolving Names in Your Code

* High-level overview of scopes:

```py
>>> # This area is the global or module scope
>>> number = 100
>>> def outer_func():
...     # This block is the local scope of outer_func()
...     # It's also the enclosing scope of inner_func()
...     def inner_func():
...         # This block is the local scope of inner_func()
...         print(number)
...
...     inner_func()
...
>>> outer_func()
100
```

* Python scope is presented using LEGB
  * **Local**
  * **Enclosing**
  * **Global**
  * **Built-in**
* Two general scopes:
  * **Global**
    * The names that you define in this scope are available to all your code
  * **Local**
    * The names that you define in this scope are only available or visible to the code within the scope
* Limiting scope reduces the chances of unintended modification of variables by other parts of the code base
* How things become available in the Python Scope
  * Variables in Python come into existence when you first assign them a value
  * Functions and classes are available only after you define them using `def` or  `class`, respectively
  * `modules` only exist after you import them
* **Python assigns scope based on location of the name assignment**
  * If you assign a value to a name inside a function, that name will have a local scope
  * If you assign it a value outside all functions, it will have a global scope
* **Namespaces**
  * A dictionary of scopes that maps name to objects
  * Has special attribute call `__dict__`
    * Names at the top level of a module are stored in the module's namespace
  * Can be accessed via .dot notation or subscription operation
    * EX: Need to access name `ps1` which is defined in `sys`

    ```py
    sys.ps1 # .dot notation
    sys.__dict__['ps1'] #subscription operation
    ```

* Using the LEGB Rule for Python Scope
  * Python looks up names in the following order:
    * **Local**
      * Code block of any Python function or `lambda` expression
      * Not accessible outside of the function
      * Creates a *function call*, not a function definition
      * Can have as many different local scopes as function calls
    * **Enclosing**
      * Special scope that only exists for nested functions
      * Enclosing scope refers to the scope enclosed by the outermost function
      * Code is visible to only the functions within the enclosed scope
    * **Global**
      * Top-most scope
      * Accessible to all functions
    * **Built-in**
      * Special scope created or loaded whenever you run a script or open an interactive sessions
      * Contains names such as `keywords`, `functions`, `exceptions`, and other attributes that are built into Python
      * These names are also available everywhere in the code
* You can use `__code__` to examine the attributes of your code:

  ```py
  def square(base):
    result = base ** 2
    print(f'The square of {base} is: {result}')

  >>> square.__code__.co_varnames
  ('base', 'result')
  >>> square.__code__.co_argcount
  1
  >>> square.__code__.co_consts
  (None, 2, 'The square of ', ' is: ')
  >>> square.__code__.co_name
  'square'
  ```

* The Global Scope
  * When you start a Python program, Python turns your main script into a module call `__main__` to hold the main program's execution
    * `__main__` is a special name reserved for the global scope
    * The namespace of this module is the global scope
  * To inspect the names within your global scope you can use `dir()` to get the list of names in the global scope
    * Example

    ```py
    >>> dir()
    ['__annotations__', '__builtins__',..., '__package__', '__spec__']
    >>> var = 100  # Assign var at the top level of __main__
    >>> dir()
    ['__annotations__', '__builtins__',..., '__package__', '__spec__', 'var']
    ```
  
  * Variables within functions *can* be assigned to the global scope using the `global` statement 
