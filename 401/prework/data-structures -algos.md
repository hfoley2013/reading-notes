# Data Structures and Algorithms

## Resources

* [Basic Recursion](https://www.youtube.com/watch?v=vPEJSJMg4jY)
* [Data Structures in 15 Minutes](https://www.youtube.com/watch?v=sVxBVvlnJsM)
* [Big O Explained](https://www.youtube.com/watch?v=v4cd1O4zkGw)
* [Basic Data Structures](https://towardsdatascience.com/8-common-data-structures-every-programmer-must-know-171acf6a1a42)
* [Why Big O](https://triplebyte.com/blog/why-you-should-learn-big-o-and-stop-hacking-your-way-through-algorithms)

## Discussion Questions

* **What is 1 of the more important things you should consider when deciding which data structure is best suited to solve a particular problem?**
  * What are you going to be doing with the data?
  * Depending on exactly what data manipulation you need to do, you can chose a more effective data structure
  * Next big thing to consider, how is the data structured and how large is the data set
* **How can we ensure that we’ll avoid an infinite recursive call stack?**
  * You have to tell the function to exit
    * You must provide a base case that allows the function to exit the loop

## Notes

### Basic Recursion

```py
def look_for_key(box):
  for item in box:
    if item.is_a_box():
      look_for_key(item)
    elif item.is_a_key():
      print "found the key!"
```

* Base Case
  * The case in which the function will stop calling itself
* Recursive Case
  * The case in which the function will continue to call itself
* In the example above:
  * `if item.is_a_box() : look_for_a_key(item)` is the recursive case
    * The function continues to call itself if the item inside a box is a box
  * `elif item.is_a_key(): print "found the key!"` is the base base
    * Once a key is found the function stops calling on itself and exits the recursion

### Data Structure in 15 Minutes

* Big O notation defines how efficient a data structure is
* Linked Lists
  * node
    * Contains a value and a pointer
      * Value can be anything
      * Pointer connects you to next node in the chain
    * First node = head
    * Last node = tail
  * Pros
    * Adding new items
    * Deleting items
  * Cons
    * Retrieval
    * Searching
      * Bad at this because each node is only aware of the node immediately adjacent to it
* Array
  * A continuous block of cells in the computer memory
  * By remembering the index location of an item, you can immediately call it
  * Pros
    * Retrieving items
  * Cons
    * Takes up a lot of memory
    * Adding new items
* Hash Table
  * Object in js or dictionary in Python
  * Uses key, value pair
  * Pros
    * Adding
    * Removing
  * Cons
    * Collisions
      * Occur when two keys hash to the same location
* Stack + Queue
  * Stack
    * LIFO data structure
      * Add item to top (.push())
      * Remove item off top (.pop())
    * Depth First Search
    * Functions are tracked via the call stack
  * Queue
    * FIFO data structure
      * Add item to end (.enqueue())
      * Remove item from front (.dequeue())
    * Breadth First Search
* Graphs + Trees
  * Maps out relationships between data
  * Tree is special kind of Graph in which the data flows in a one way hierarchy (parent to child(ren))
  * Binary Search Tree
    * Each node can have max 2 children (0-2 children)
    * Left < node
    * Right > node

### Big O Notation

* Measures how efficient an algorithm is
* Rules
  * Different steps get added
    * EX:

      ```
      function something () {
        do1(); //O(a)
        do2(); //O(b)
      }
      //total time: O(a+b)
      ```
  
  * Constants get dropped
  * Different inputs get different variables
  * Drop non-dominate terms
