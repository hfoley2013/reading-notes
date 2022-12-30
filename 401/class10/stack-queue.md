# Stacks and Queues

## Readings

* [Stacks and Queues](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)

## Notes

### Stacks

* What is a stack?
  * A data structure that consists of `Nodes`
  * Each `Node` references the next `Node` in the stack, but *not* the previous
* Stack Terminology
  * *Push* - Nodes or items that are put into the stack are pushed
    * Push = added to the stack
  * *Pop* - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
    * Pop = remove from the stack
  * *Top* - This is the top of the stack.
  * Peek - When you `peek` you will view the value of the top Node in the stack. When you attempt to `peek` an empty stack an exception will be raised.
  * *IsEmpty* - returns true when stack is empty otherwise returns false.
* Stack Concepts
  * **F**irst **I**n **L**ast **O**ut
    * First item added to the stack is the last item popped out of the stack
  * **L**ast **I**n **F**irst **O**ut
    * The last item added to the stack is the first item popped off the stack
  * Stack Visualization

    ![Stack Visual](./stack_visual.png)

    * The topmost item it denoted as `top`
    * When you `push` something to the stack, it becomes the new `top`
    * When you `pop` something off the stack, you remove the current `top` and set the next `top` as `top.next`
* Stack Operation Details
  * Push
    * O(1)
      * Always takes the same amount of time no matter how many `Nodes` are in the stack since you are *always* pushing to the top of the stack
    * When adding a `Node`, you `push` it to the stack by assigning it as the new `top` with its `next` property equal to the old `top`
    * Steps
      1. Connect the new `top` to the old `top` by setting the `top.next` property to equal the old `top`
         * ![Push Operation 1: Assign top.next](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/pushStack2.PNG)
      2. Assign the `top` value equal to the value of the new `Node`
         * ![Push Operation 2: Assign new top](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/pushStack3.PNG)
    * Code example

      ```py
      ALOGORITHM push(value)
      // INPUT <-- value to add, wrapped in Node internally
      // OUTPUT <-- none
        node = new Node(value)
        node.next <-- Top
        top <-- Node
      ```

  * Pop
    * O(1)
      * Always takes the same about of time to `pop` a node off the stack since you are always removing one off the top of the stack
    * When you `pop` a `Node` off the stack, first you check `isEmpty` to ensure no exception is raised, then you set a `temp` variable to hold the old `top`, then you assign the value of `top` to the value that the `next` property is referencing, then you clear the `next` reference in the `temp` variable, then return `temp` to the user
    * Steps
      1. Create a `temp` variable and assign the current `top` to it
         * ![Pop Operation 1: Create temp](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/popStack2.PNG)
      2. Assign the `top` value to the `temp.next` property
         * ![Pop Operation 2: Reassign top](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/popStack3.PNG)
      3. Clear out the `next` property in the `temp` variable
         * ![Pop Operation 3: Clear temp.next and return temp](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/popStack4.PNG)
      4. Return `temp` to the user
    * Code example

      ```py
      ALGORITHM pop()
      // INPUT <-- No input
      // OUTPUT <-- value of top Node in stack
      // EXCEPTION if stack is empty

        Node temp <-- top
        top <-- top.next
        temp.next <-- null
        return temp.value
      ```
  
  * Peek
    * O(1)
      * `peek` only looks at the `top` Node of the stack
    * Looks inside and returns `top.value` if the stack is not empty
    * Code example

      ```py
      ALGORITHM peek()
      // INPUT <-- none
      // OUTPUT <-- value of top Node in stack
      // EXCEPTION if stack is empty

        return top.value
      ```

  * IsEmpty
    * O(1)
    * Code example

    ```py
    ALGORITHM isEmpty()
    // INPUT <-- none
    // OUTPUT <-- boolean

    return top = NULL
    ```

### Queues

* What is a queue?
  * First In First Out, Last In Last Out data structure
* Queue Terminology
  * **Enqueue** - Nodes or items that are added to the queue.
  * **Dequeue** - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
  * **Front** - This is the front/first Node of the queue.
  * **Rear** - This is the rear/last Node of the queue.
  * **Peek** - When you `peek` you will view the value of the `front` Node in the queue. If called when the queue is empty an exception will be raised.
  * **IsEmpty** - returns true when queue is empty otherwise returns false.
* Queue Visualization
  * ![Queue Visual](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Queue.PNG)
* Queue Operations
  * Enqueue
    * O(1)
    * Adds item to the back of the queue
    * Steps
      1. Assign the `next` property of the last Node in the queue to the value of the new Node
         * ![Enqueue Operation 1: Assign next property to new Node](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Enqueue2.PNG)
    * Code example

      ```py
      ALGORITHM enqueue(value)
      // INPUT <-- value to add to queue (will be wrapped in Node internally)
      // OUTPUT <-- none
        node = new Node(value)
        rear.next <-- node
        rear <-- node
        ```

  * Dequeue
    * O(1)
    * Removes item from front of queue and returns it to the user
    * Steps
      1. Create a `temp` variable and assign front Node to it
         * ![Dequeue Operation 1: Create temp variable](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Dequeue1.PNG)
      2. Clear the `temp.next` attribute and return `temp` to the user
         * ![Dequeue Operation 2: Clear temp.next, return temp](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Dequeue3.PNG)
    * Code Example

      ```py
      ALGORITHM dequeue()
      // INPUT <-- none
      // OUTPUT <-- value of the removed Node
      // EXCEPTION if queue is empty

        Node temp <-- front
        front <-- front.next
        temp.next <-- null

        return temp.value
        ```
  
  * Peek
    * O(1)
    * Inspects the `front` node and returns its value
    * Code example

      ```py
      ALGORITHM peek()
      // INPUT <-- none
      // OUTPUT <-- value of the front Node in Queue
      // EXCEPTION if Queue is empty

        return front.value
        ```
  
  * IsEmpty
    * O(1)
    * Checks to see if queue is empty and returns a boolean
    * Code example

      ```py
      ALGORITHM isEmpty()
      // INPUT <-- none
      // OUTPUT <-- boolean

      return front = NULL
      ```
