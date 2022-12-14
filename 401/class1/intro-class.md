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
