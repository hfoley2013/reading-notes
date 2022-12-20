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
