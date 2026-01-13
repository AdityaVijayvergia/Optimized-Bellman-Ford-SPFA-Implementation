### Optimized Bellman-Ford (SPFA) Implementation

**Description:**
This repository hosts a C++ implementation of an optimized graph shortest-path algorithm derived from Bellman-Ford, commonly referred to as the **Shortest Path Faster Algorithm (SPFA)**.

While the standard Bellman-Ford algorithm blindly relaxes all edges  times, this implementation utilizes a **queue-based strategy**. It tracks only those nodes whose shortest path estimates have been updated, adding them to a queue for processing. This approach drastically reduces unnecessary computations, offering significantly better average-case performance—typically  where  is small—making it highly efficient for sparse graphs while retaining the ability to handle negative edge weights.

**Key Features:**

* **Queue-Based Optimization:** Eliminates redundant edge relaxations by processing only "active" nodes.
* **Dynamic Updates:** Efficiently propagates distance updates through the graph.
* **Undirected Graph Support:** The current implementation supports weighted undirected graphs.
* **Negative Weights:** Capable of calculating shortest paths in graphs with negative edge weights (unlike Dijkstra's algorithm).

**How it Works:**

1. Initializes distances to infinity, with the source node set to 0.
2. Push the source node into a queue.
3. While the queue is not empty:
   * Pop a node .
   * Iterate through all neighbors  of .
   * If the path to  through  is shorter than the current known path, update 's distance and push  into the queue (if not already present).
