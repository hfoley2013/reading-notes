# Intro to 401: Python

## Reading

* [Pain and Suffering](https://codefellows.github.io/code-401-python-guide/curriculum/class-01/notes/pain_suffering)
* [Beginners Guide to Big O](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/)
* [A Friendly into to Big O Notation](https://www.codenewbie.org/basecs/8)
* [Names and Values in Python](https://www.youtube.com/watch?v=_AEJHKGk9ns)
* [Awesome Python Environment](https://towardsdatascience.com/how-to-setup-an-awesome-python-environment-for-data-science-or-anything-else-35d358cc95d5)
* [Python Module of the Week](https://pymotw.com/3/index.html)

## Notes

### Pain and Suffering

* **BLUF**
  * Growth comes with the price of *pain*
  * Pain is a given, suffering is a choice
  * Suffering is choosing to view the pain as painful for its own sake
  * Taking an attitude of viewing the pain as growth will remove the suffering element
  * Choose to view the course as a challenge, not as tortuous, and you will not suffer

### Beginners Guide to Big O

* What is *Big O*?
  * Notation that describes the complexity of an algorithm
* `O(1)`
  * Always executes in the same time (or space) regardless of the size of the input data set

  ```py
  bool IsFirstElementNull(IList<String> elements)
  {
      return elements[0] == null;
  }
  ```

* `O(N)`
  * Performance grows linearly and in direct proportion to the size of the input data set
  * Big O favors the ***worst case*** performance scenario, meaning it will assume the longest execution timeframe possible

  ```py
  bool ContainsValue(IEnumerable<string> elements, string value)
  {
      foreach (var element in elements)
      {
          if (element == value) return true; 
      }     
      return false; 
  }
  ```

* `O(N^2)`
  * Performance is directly proportional to the square of the size of the input data set
  * Common for nested iterations

  ```py
  bool ContainsDuplicates(IList<string> elements)
  {
      for (var outer = 0; outer < elements.Count; outer++) 
      {
          for (var inner = 0; inner < elements.Count; inner++) 
          { 
              // Don't compare with self 
              if (outer == inner) continue;             
              
              if (elements[outer] == elements[inner]) return true; 
          }
      }    
      return false;
  }
  ```

* `O(2^N)`
  * Growth double with each addition to the input data set
  * Growth is exponential

  ```py
  int Fibonacci(int number)
  {
      if (number <= 1) return number;
        
      return Fibonacci(number - 2) + Fibonacci(number - 1); 
  }
  ```

* `O(log N)`
  * Growth curve peaks at the beginning and slowly flattens out as more data is feed into the process
  * Common for binary search algos that using having logic to find a value
  * Doubling or 100x the data set doesn't have a great effect on processing time
  * Logarithms are extremely efficient when dealing with large data sets

### Python Names and Values

* Names refer to values
  * `x = 23` => x is assigned the value of 23
* Code executes in order from top to bottom

  ```py
  x = 23
  y = x
  x = 12
  print(y) //=> y = 23
  print(x) //=> x = 12
  ```

* Values live until no references
  * Once all references are gone, the value disappears
* **Assignment never copies data**
  * This means that Named values cannot be reassigned!
    * I.E. if you want to create a copy of a list by changing the name of the reference, you will only assign the original list to the new name. Any modifications done to the original list will be reflected in the new reference as well
  * The above is know as ***Mutable aliasing***
    * Occurs when:
      * A mutable value
      * More than one name
      * The value changes
      * All names see the change!
* ***Immutables values can't alias***
  * Immutable types: `ints, floats, strings, tuples`
* "Change" is unclear
  * Changing an int: `rebinding`
    * `x = x + 1`
    * In this case, we are *rebinding* the value of `x` to the value of `x + 1`
  * Changing a list: `mutating`
    * `nums.append(7)`
    * The list is *mutated* to append `7` to the end of the list
  * Cannot mutate an `int`: `int` is **immutable**
* Mutable and immutable are assigned the same way
  * Assignment is the same for **all** values
  * Aliasing can make it seem different
* References can be more than just names
  * List elements
  * Object attributes
  * Dict keys and values
  * **Anything on the left side of an assignment**
* For loops
  * In a `for` loop, we constantly assign new values to `x` as we go through the sequence
* Function arguments are assignments
  * Local variables inside a function will disappear once the function returns if the variable isn't passed to the global scope
  * You can assign a return value to a name in the global scope by assigning the entire function to the name
* ***Make a new list***
* Any name can refer to any value at any time
* Name have no type, values have no scope
* Python is neither call-by-value or call-by-reference, it is call-by-assignment
  * When you call a value you are assigning it to the name used to call it

### How to Setup an Awesome Python Environment

* **The Interpreter**
  * Allows you to switch between programs that require different versions of Python or 3rd party modules seamlessly
  * Can use Pyenv
    * `curl https://pyenv.run | bash`

    ```
    export PATH="~/.pyenv/bin:$PATH"
    eval "$(pyenv init -)"
    eval "$(pyenv virtualenv-init -)"
    ```

  * For Ubuntu machine, you will need the following:

  ```
  sudo apt-get install build-essential libsqlite3-dev sqlite3 bzip2 libbz2-dev zlib1g-dev libssl-dev openssl libgdbm-dev libgdbm-compat-dev liblzma-dev libreadline-dev libncursesw5-dev libffi-dev uuid-dev
  ```

  * To install Python run:
    * `pyenv install VERSION_YOU_WOULD_LIKE_TO_INSTALL`

* Dependency Management
  * [Poetry](https://poetry.eustace.io/)
    * Helps with the following:
      * Manage your projects’ dependencies
      * Separate your projects through virtual environments
      * Build both applications as well as libraries without headaches

    * Install via `curl`
    ```
    curl -sSL 
    https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python
    ```

    * Install via `pip`

    ```
    # Create a virtual environment called tools that is based on 3.7.5
    pyenv virtualenv 3.7.5 tools 
    # Install poetry into the tools virtual env
    pyenv activate tools
    pip install poetry 
    # Check installed poetry version
    poetry --version
    # Leave the virtual env 
    pyenv deactivate 
    # This does not work yet 
    poetry --version
    # Add your tools virtual env to the globally available ones
    pyenv global 3.7.5 tools
    # Now this works and you can start using poetry
    poetry --version
    ```
  
  * Configure so that the virtual environment is created *inside* your project folder

    ```
    # That seems to be peotry prior to 1.0.0
    poetry config settings.virtualenvs.in-project true
    # That is poetry since 1.0.0
    poetry config virtualenvs.in-project true
    ```
  
  * Initializing a new project

    ```
    # Initialze a new project
    poetry new dsexample 
    cd dsexample
    # Add modules and create virtual environment.
    poetry add pandas=0.25 fastapi --extras all
    # As an example of how you could add a git module
    poetry add tf2-utils --git git@github.com:Shawe82/tf2-utils.git
    ```

* Consistent Formatting and Readability
  * [Black](https://black.readthedocs.io/en/stable/)
    * Automates code formatting so you can avoid manually doing it
    * Installation

      ```
      # We add black as a development dependency with --dev as we don't
      # need it when it comes to production
      poetry add --dev black=19.3b0
      # Assume we are inside the current toplevel dsexample folder
      poetry run black .
      ```

* Type-Correctness
  * [mypy](https://mypy.readthedocs.io/)
    * Static type checker for python code, that finds errors before they appear
      * Can check that the type of the variable is the same as what you expect
    * Install

      ```
      # We add mypy as a development dependency with --dev as we don't
      # need it when it comes to production
      poetry add --dev mypy
      # Assume we are inside the current toplevel dsexample folder
      poetry run mypy .
      ```

    * Config
      * [Documentation](https://mypy.readthedocs.io/en/latest/config_file.html)
      * Configure it to only warn you about the things you are interested in by adding a mypy.ini file to your project

* Automate the Automation
  * [Pre-Commit](https://pre-commit.com/)
    * Allows you to auto-run the tools installed above
    * Will fail if the tools above run into any errors and will not commit the code base
  * Install

  ```
  # Install pre-commit into the tools virtual env
  pyenv activate tools
  pip install pre-commit 
  # Leave the virtual env 
  pyenv deactivate
  # As we have already added the tool venv, it will work directly
  pre-commit --version
  ```

  * To use:
    * First, add a config file called .pre-commit-config.yaml to the top-level folder of your project
      * In that file, you configure all the hooks that should run
    * Example

      ```
      repos:
      -   repo: https://github.com/ambv/black
          rev: 19.3b0
          hooks:
          - id: black
            language_version: python3.7
      -   repo: https://github.com/pre-commit/mirrors-mypy
          rev: v0.740
          hooks:
          - id: mypy
      ```
      
      * Next, you must tell pre-commit to set up the hooks by executing

        ```
        # I assume your are in the top level folder
        pre-commit install
        ```

        * Now the hooks will run on every commit!
      * To run, execute:
        * `pre-commit run --all-files`
