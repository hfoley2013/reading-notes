# Linked Lists

## Reference

* [Linked List Overview](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)
* [What is a Linked List Anyway? Part 1](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)
* [What is a Linked List Anyway? Part 2](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)

## What is a Linked List?

A linked list is a **linear data structure** in which each element is a separate object that is connected to the next element in the list using a pointer. Linked lists are ***dynamic data structures***, meaning they can **grow or shrink as needed** during the execution of a program. This is in contrast to arrays, which have a fixed size and must be created with that size in mind.

## Advantages of Linked Lists

One advantage of linked lists is that they can be **easily inserted or removed from the middle of the list**, because there is no need to shift elements around to make room for a new element or to fill the gap left by a deleted element. This makes linked lists **well-suited for situations where elements will be added or removed frequently.**

## Disadvantages of Linked Lists

However, there are also some trade-offs to consider when using linked lists. One disadvantage is that they are generally **slower than arrays when it comes to accessing individual elements**, because each element *must* be accessed by following the pointers from one element to the next. This can make linked lists less efficient for situations where elements will be accessed randomly or frequently.

Another disadvantage of linked lists is that they **require more memory than arrays**, because each element in a linked list requires an additional pointer to store the address of the next element in the list. This can make linked lists less memory-efficient than arrays, especially for large lists.

## Summary

Overall, the choice between using a linked list or an array will depend on the specific needs of the application. **If you need to frequently insert or delete elements and memory usage is not a concern, a linked list may be a good choice.** If you need fast access to individual elements and memory usage is a concern, an array may be a better choice.

## Terminology

* **Linked List** - A data structure that contains nodes that links/points to the next node in the list.
* **Singly** - Singly refers to the number of references the node has. A `Singly` linked list means that there is only one reference, and the reference points to the `Next` node in a linked list.
* **Doubly** - Doubly refers to there being two (double) references within the node. A `Doubly` linked list means that there is a reference to both the `Next` and `Previous` node.
* **Node** - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.
* **Next** - Each node contains a property called `Next`. This property contains the reference to the next node.
* **Head** - The `Head` is a reference of type `Node` to the first node in a linked list.
* **Current** - The `Current` is a reference of type `Node` to the node that is currently being looked at. When traversing, you create a new `Current` variable at the `Head` to guarantee you are starting from the beginning of the linked list.

## Linked List Example

![Linked List](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/LinkedList1.PNG)

## Traversing a Linked List

* ***Cannot use a `for` or `for each` loop***
* Must use the `Next` value in each node to direct us to the next reference point
* Recommended to use a `while` loop during traversal, setting the `Current` value equal to the `Next` value

  ```py
  ALGORITHM Includes (value)
  // INPUT <-- integer value
  // OUTPUT <-- boolean

  Current <-- Head

  WHILE Current is not NULL
    IF Current.Value is equal to value
      return TRUE

    Current <-- Current.Next

  return FALSE
  ```

* Traversal Big O
  * **Time:** O(n) because, at its worse case, the node we are looking for will be the very last node in the linked list
    * `n` represents the number of nodes in the linked list.
  * **Space:** O(1) because there is no additional space being used than what is already given to us with the linked list input

## Adding a Node
