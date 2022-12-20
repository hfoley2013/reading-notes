# Testing and Modules

## References

* [In Tests We Trust - TDD with Python](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)
* [If name equals main](https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/)
* [Recursion](https://www.geeksforgeeks.org/recursion/)
* [What on Earth is Recursion](https://www.youtube.com/watch?v=Mv9NEXX1VHc)
* [Python Modules and Packages Companion Video](https://realpython.com/courses/python-modules-packages/)
* [Google for Education: Python Lists](https://developers.google.com/edu/python/lists)
* [Google for Education: Python Strings](https://developers.google.com/edu/python/strings)
* [Python Modules and Packages](https://realpython.com/python-modules-packages/)
* [Pytest Documentation](https://docs.pytest.org/en/latest/)
* [PyTest Tutorial Up to section Running tests in parallel](https://www.guru99.com/pytest-tutorial.html)

## Summary: Why is this important?

* Understanding how to write strong unit tests will prevent errors in your code from the beginning if you start with building out your tests.
* Starting with the question, "How do I validate that the code is functioning the way it should?", forces you to think about exactly what data and data type you are expecting your program to return.
* This allows you to think more robustly about how you will write out your code to pass tests that will ensure it is functioning properly.
* Recursion is a powerful tool available to us to complete iterative tasks in a much more readable manner with less code, though it does carry with it the risk of **stack overflow** if the base and recursive cases are not set properly
* Modular programming in Python allows us to reduce complexity by designing modules that function to solve a specific problem within our program.
  * This makes building and auditing individual modules much more simple that a much more complex code base jammed into one file.


## Notes

### In Tests We Trust - TDD with Python

* TDD = Test Driven Development
* Write Tests first
* Give descriptive names to your tests
  * EX: `def test_should_return_female_when_the_name_is_from_female_gender():`
* Name of the test module should follow the same name of the module to be tested
  * EX: module is `markets.py`, the test should be `test_markets.py`
* Structure of tests (AAA)
  * **Arrange**
    * Organize the data to execute the piece of code (input)
  * **Act**
    * Execute the code being tested (exercise the behavior)
  * **Assert**
    * Check if the result (output) is the same as you were expecting

  ```py
  def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’
  ```

* The TDD Cycle
  * 🆘 Write a unit test and make it fail (it needs to fail because the feature isn’t there at first)
  * ✅ Write the feature and make the test pass
  * 🔵 Refactor the code

### What does the if __name__ == “__main__”: do?

* Python files can act as either reusable modules, or as standalone programs.
* If you import this script as a module in another script, the __name__ is set to the name of the script/module.
* If the module is being run standalone by the user then the module __name__ is ‘__main__’ and can do corresponding appropriate actions.
* if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported.

### Recursion

* Base code
  * The code that stops the recursion when a condition is met
* Recursive code
  * The code that continues to call itself until a condition is met
* Recursive functions use LIFO in the call stack
  * Because the function keeps referencing itself until a condition is met, stack frames will pile up and eat up memory until the condition is met
  * Once the condition is met, the call stack will return the stack frames in a LIFO manners until the final answer is returned
* Direct Recursion
  * Direct recursion occurs when a function (fun) calls itself within the function

    ```js
    void directFun(){
      //some code
      directFun();
      //more code
    };
    ```

* Indirect Recursion
  * Indirect recursion occurs when two functions call each other directly or indirectly until a condition is met

    ```js
    void indirectFun1(){
      //code
      indirectFun2();
      //code
    }
    void indirectFun2(){
      //code
      indirectFun1();
      //code
    }
    ```

### Modular Programming in Python

* Modular programming is breaking large programs into separate, smaller, more manageable subtasks (modules)
* Advantages
  * Simplicity
    * Allows the modules to focus on one problem and solve it
  * Maintainability
    * Minimizes interdependency so can be more readily modified
  * Reusability
    * Modules can be reused by other parts of the program, reducing duplicate code
  * Scoping
    * Modules typically have separate namespace, which reduces the change of collisions between identifiers in different areas of the program
* Modules must be imported into other parts of the program where they are to be used
  * `import <module_name>`
* Names of objects defined in the module ***must*** be prefixed by the module name and accessed via **dot notation**
  * Exception to this is when they are explicitly imported using `from <module_name> import <name(s)> as <alt_name>`
    * Objects can now be accessed directly via their `<name(s)>`
    * **NOTE:** the `as <alt_name>` is optional
