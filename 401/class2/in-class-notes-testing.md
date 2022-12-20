# In Class Notes: Testing and Modules

* `pip install pytest` inside the virtual environment
  * This keeps the package confined to the specific program you are working on
* Need to create a `test` folder and a `test_<module-name>.py` file

## Process

* Create project
* Activate virtual environment
* Create `tests` folder
* Create a `test_<module-name>.py` file for each test you want to build
* We will start by writing a test for the program based on our desired outputs
  * **NOTE:** tests must begin with `test_<test-name>():`
* Import pytest into `test_<module-name>.py` file
  `import pytest`
* Create a `__init__.py` file within the `tests` folder in order for tests to initialization
* Install `pytest-watch`
  * This library always watches for changes inside the test file
  * This will let you know if your test begin to fail due to errors you just made
* Import the desired functions to test into the appropriate test module
  * `from <module-name> import <function-name>`
* Can skip tests by placing `@pytest.mark.skip()` on the line proceeding the function you want to skip
* **NOTE:** When you first run a test it will fail because you have not yet built the function
