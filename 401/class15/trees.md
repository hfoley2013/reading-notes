# Trees

## Reading

* [Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)

## Notes

### What is a tree?

A tree is a commonly used abstract data type that simulates a hierarchical tree structure, with a set of nodes or vertices, and edges connecting them. Each node in the tree has a value and may have one or more child nodes. The topmost node in the tree is called the root node, and there is no parent node for the root node. Each node in the tree, except for the root node, has exactly one parent node. The edges connecting the nodes represent the relationships between the nodes.

Trees are often used to represent hierarchical relationships between entities, such as the structure of a directory on a computer, or the relationships between elements in an XML document. They can also be used to represent decision-making structures, such as in a flowchart or a decision tree.

There are many different types of trees, including binary trees, AVL trees, red-black trees, and others, each with its own specific characteristics and applications.

![Tree](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)

### What is a binary search tree?

A binary search tree (BST) is a type of binary tree where the value of each node in the tree is greater than or equal to the values in its left child and less than or equal to the values in its right child. This property, known as the BST property, allows the tree to be searched quickly, making it a useful data structure for storing and accessing data.

The basic operations that can be performed on a binary search tree include inserting a new node, deleting a node, and searching for a particular node. The time complexity of these operations depends on the height of the tree, with the average-case time complexity being O(log n) for a tree with n nodes.

Binary search trees are used in a wide variety of applications, including computer science, engineering, and finance, where they can be used to store and quickly access data such as integers, floating point numbers, and strings.

![Binary Search Tree](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BST2.PNG)

### What is a K-Ary Tree?

A K-ary tree is a tree data structure in which each node can have up to K children. This is in contrast to a binary tree, which has a maximum of two children (known as left and right children), or a ternary tree, which has a maximum of three children.

K-ary trees are often used when it is necessary to store and access data that has a hierarchical structure, such as a file system or a database index. They can be searched and modified efficiently, with the time complexity of the basic operations (insertion, deletion, and search) being O(log n) on average for a tree with n nodes.

One of the main advantages of K-ary trees is that they can have a smaller height (i.e., the maximum distance from the root to a leaf node) than binary trees with the same number of nodes, which can make them more efficient in terms of space and time complexity. However, they do require more space to store the additional child pointers for each node.

![K-Ary Tree](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/KaryTree1.png)

### What is depth first traversal?

Depth first traversal is a method of traversing a tree or graph data structure in which the algorithm begins at the root node and explores as far as possible along each branch before backtracking. There are three common methods of depth first traversal: in-order, pre-order, and post-order.

In an in-order traversal, the left subtree of the current node is visited first, then the current node itself, and finally the right subtree. This results in the nodes being visited in ascending order, if the tree is a binary search tree.

In a pre-order traversal, the current node is visited first, followed by the left subtree, and then the right subtree.

In a post-order traversal, the left subtree is visited first, followed by the right subtree, and finally the current node itself.

Depth first traversal is often used to search for a specific node in a tree, or to visit all the nodes in the tree in a specific order. It can also be used to generate a topological sort of a directed acyclic graph (DAG).

```py
class Node:
    def __init__(self, value, left=None, right=None):
        self.value = value
        self.left = left
        self.right = right

def pre_order_traverse(node):
    if node:
        print(node.value)
        pre_order_traverse(node.left)
        pre_order_traverse(node.right)

root = Node(1, Node(2, Node(4), Node(5)), Node(3, Node(6), Node(7)))
pre_order_traverse(root)
```

This will print the values of the nodes in the following order: 1, 2, 4, 5, 3, 6, 7.

To implement an in-order or post-order traversal, you would simply need to adjust the order in which the left, current, and right nodes are visited.

![Step 1](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal1.PNG)
![Step 2](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal1.PNG)
![Step 3](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal3.PNG)
![Step 4](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal4.PNG)
![Step 5](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal5.PNG)
![Step 6](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal6.PNG)
![Step 7](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal7.PNG)
![Step 8](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal8.PNG)
![Step 9](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal9.PNG)
![Step 10](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal10.PNG)
![Step 11](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/DepthTraversal11.PNG)


### What is breadth first traversal?

Breadth first traversal is a method of traversing a tree or graph data structure in which the algorithm begins at the root node and explores all the neighboring nodes at the present depth level before moving on to the nodes at the next depth level.

In a breadth first traversal, the nodes are visited in the order in which they are encountered, starting at the root node and moving across each level of the tree from left to right. This can be implemented using a queue to store the nodes that are waiting to be visited.

Breadth first traversal is often used to search for a specific node in a tree, or to visit all the nodes in the tree in a specific order. It can also be used to find the shortest path between two nodes in a graph, or to solve other problems such as finding the shortest path in a maze.

```py
class Node:
    def __init__(self, value, left=None, right=None):
        self.value = value
        self.left = left
        self.right = right

def breadth_first_traverse(root):
    queue = [root]
    while queue:
        node = queue.pop(0)
        print(node.value)
        if node.left:
            queue.append(node.left)
        if node.right:
            queue.append(node.right)

root = Node(1, Node(2, Node(4), Node(5)), Node(3, Node(6), Node(7)))
breadth_first_traverse(root)
```

This will print the values of the nodes in the following order: 1, 2, 3, 4, 5, 6, 7.

![Step 1](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthTraversal1.PNG)
![Step 2](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthTraversal2.PNG)
![Step 3](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthTraversal3.PNG)
![Step 4](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthTraversal4.PNG)
![Step 5](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthTraversal5.PNG)
![Step 6](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthTraversal6.PNG)
![Step 7](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthTraversal7.PNG)
![Step 8](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthTraversal8.PNG)
