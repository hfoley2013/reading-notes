# Classes & Objects

## References

* [Classes & Objects](https://www.learnpython.org/en/Classes_and_Objects)
* [Thinking Recursively](https://realpython.com/python-thinking-recursively/)
* [Pytest Fixtures & Coverage](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)
* [Bookmark: Pytest Fixtures](https://docs.pytest.org/en/latest/fixture.html)

## Notes

### Classes & Objects in Python

* Classes are templates to create objects
* Objects are a combination of variables and functions into one element
* Basic syntax

  ```py
  class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")
  ```

* Can change the value of variables within a class by referencing them using .dot notation

  ```py
  myobjectx = MyClass()
  myobjecty = MyClass()

  myobjecty.variable = 'ahhhh'

  print(myobjectx.variable)
  print(myobjecty.variable)
  """
  prints:
  blah
  ahhhh
  """
  ```

* Can also access contained functions via .dot notation as well

  ```py
  myobjectx.function()

  """
  prints
  "This is a message from inside the class."
  """
  ```

### Thinking Recursively in Python

* Recursive functions are functions that call themselves given a set of conditions
  * Need a base case and recursive case
    * Base Case = condition in which the recursion will stop
    * Recursive Case = conditions in which the function will self reference
* Recursion ties up a significant amount of memory in the call stack
  * Recursion is LIFO, so the more times a function has to call itself, the more frames get added to the call stack
  * Once the base case is met, the frames come in LIFO and return the result
* Since each recursive call has it's own execution context you must do one of the following to maintain state during recursion:
  * Thread the state through each recursive call so that the current state is part of the current call’s execution context
  * Keep the state in global scope
  * Threading example summing values 1 to 11

    ```py
    def sum_recursive(current_number, accumulated_sum):
    # Base case
    # Return the final state
    if current_number == 11:
        return accumulated_sum

    # Recursive case
    # Thread the state through the recursive call
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)
    ```

  * Global scope example

    ```py
    # Global mutable state
    current_number = 1
    accumulated_sum = 0


    def sum_recursive():
        global current_number
        global accumulated_sum
        # Base case
        if current_number == 11:
            return accumulated_sum
        # Recursive case
        else:
            accumulated_sum = accumulated_sum + current_number
            current_number = current_number + 1
            return sum_recursive()
    ```

* Recursive data structures
  * A data structure is recursive if it can be defined in terms of a smaller version of itself
  * Common types
    * Lists
    * Trees
    * Sets
    * Dictionaries

### Fixtures in Pytest

* **Parameterized Tests** = tests with similar characteristics
* **Fixtures** = "global variables" available to all tests for use
  * Created with `@pytest.fixture` decorator followed by a function definition
