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

* TODO
