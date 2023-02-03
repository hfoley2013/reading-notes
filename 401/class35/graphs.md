# Graphs

## Readings

* [Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)

## Notes

### What are Graphs?

* Graphical representations of nodes (*vertices*) and edges that depict the relationships between objects or data.
* Each node in a graph represents an object or data, and the edges between the nodes depict the relationships between the objects or data.
* Edges can be directed or undirected, indicating the flow or lack of flow between nodes. * The structure of a node graph provides insights into the relationships between objects and can be used to solve problems such as finding the shortest path between two nodes.

### Definitions

* **Vertex**
  * A.K.A. a node
  * Fundamental unit of a graph, representing an object or data point.
  * Defined as a point where two or more edges meet.
  * In a node graph, vertices represent the objects or data and the edges represent the relationships between them.
  * Vertex properties such as weight, color, and label can be assigned to provide additional information about the object or data it represents.
* **Order**
  * The number of vertices in a graph.
  * A measure of the size of the graph and is represented by the symbol "|V|".
  * A graph with `n` vertices is said to have an order of `n`.
* **Size**
  * The number of edges in a graph.
  * A measure of the complexity of the graph and is represented by the symbol "|E|".
  * A graph with "m" edges is said to have a size of "m".
* **Edge**
  * Represent the relationships or connections between the objects or data represented by the vertices.
  * An edge can be *directed* or *undirected*, indicating the flow or lack of flow between the vertices.
  * Edges can also have additional properties such as weight, color, and label to provide additional information about the relationship between the vertices.
  * The number of edges in a graph is referred to as its size.
  * **Directed edges**
    * A.K.A. arcs
    * Indicate a **one-way relationship** from one vertex to another.

    ![Directed Edges](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DirectedGraph.PNG)

  * **Undirected edges**
    * Indicate a **two-way relationship** between vertices.

    ![Undirected Edges](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG)
