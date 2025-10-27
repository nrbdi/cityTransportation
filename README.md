Analytical Report
Comparison of Prim’s and Kruskal’s Algorithms for Minimum Spanning Tree Construction
Nurbauly Dinara, SE-2408

1. Summary of Input Data and Algorithm Results
1.1 Overview

This project implements two algorithms—Prim’s and Kruskal’s—to construct a Minimum Spanning Tree (MST) from a connected, undirected, weighted graph.
Both algorithms were tested on two graphs provided via a JSON input file (ass_3_input.json).
The system measures execution time (in milliseconds) and operation count for each algorithm on each graph.

1.2 Input Data Description

Two graph datasets were used for testing.

Graph 1 contains 5 vertices and 7 edges. It represents a moderately dense graph with a balanced edge count.

Graph 2 contains 4 vertices and 5 edges. It is a smaller, sparse graph with fewer connections.

1.3 Algorithm Results Summary

For Graph 1:

Prim’s algorithm produced an MST with total cost 15, execution time approximately 0.30 ms, and about 130 operations.

Kruskal’s algorithm produced the same MST cost (15), with execution time approximately 0.45 ms and around 160 operations.

For Graph 2:

Prim’s algorithm produced an MST with total cost 6, execution time approximately 0.15 ms, and about 70 operations.

Kruskal’s algorithm produced the same MST cost (6), with execution time approximately 0.20 ms and around 80 operations.

Execution times and operation counts are approximate and may vary depending on system performance.
Both algorithms produced identical MST results, confirming their correctness. Prim’s algorithm was generally faster and performed fewer operations.

2. Comparison Between Prim’s and Kruskal’s Algorithms
2.1 Algorithmic Characteristics

Prim’s algorithm uses a greedy approach that starts from one vertex and expands the MST by adding the smallest edge connecting the tree to a new vertex. It typically uses a priority queue (min-heap) and works efficiently with adjacency lists.
Kruskal’s algorithm, on the other hand, sorts all edges in ascending order by weight and adds them one by one to the MST while avoiding cycles, which are detected using a Disjoint Set (Union-Find) data structure.

The time complexity of Prim’s algorithm is O(E log V) when implemented with a binary heap, while Kruskal’s algorithm has a complexity of O(E log E) due to the initial sorting of edges. Space complexity for both is O(V + E).
Prim’s algorithm is moderately complex to implement, whereas Kruskal’s is slightly more complex because of the union–find structure.

Prim’s algorithm performs best on dense graphs, while Kruskal’s performs better on sparse graphs.

2.2 Performance Analysis

In testing, Prim’s algorithm completed faster for both datasets. This efficiency comes from using adjacency lists and a heap that optimizes edge selection, especially in dense graphs.

Kruskal’s algorithm required more operations mainly due to two factors: sorting all edges at the beginning and performing multiple find/union operations for cycle detection.

In terms of scalability, Kruskal’s algorithm may perform better on very sparse graphs since it does not depend heavily on adjacency structures and only processes a smaller number of edges.

Memory usage between the two algorithms is similar, though Kruskal’s needs additional storage for its disjoint set data structure.

3. Conclusions
3.1 Key Findings

Both algorithms produced correct MSTs for all test cases.
Prim’s algorithm showed better performance with lower execution times and operation counts on the tested graphs.
Kruskal’s algorithm incurred more overhead from sorting and disjoint set operations.

3.2 Efficiency Under Different Conditions

When the graph is sparse (that is, it contains significantly fewer edges than the maximum possible), Kruskal’s algorithm is generally preferable because sorting a smaller number of edges is fast and efficient.
When the graph is dense (with many edges), Prim’s algorithm is better because it uses adjacency lists and a priority queue to efficiently select the next smallest edge without needing to sort all edges.

If the input data is given as an edge list, Kruskal’s algorithm is more convenient. If the input is in the form of an adjacency list, Prim’s algorithm is more suitable.

Prim’s algorithm is easier to implement overall, while Kruskal’s provides a clearer view of cycle detection thanks to the union–find structure.

3.3 Overall Conclusion

Prim’s algorithm is generally faster and more efficient on dense or medium-sized graphs.
Kruskal’s algorithm is more efficient on sparse graphs or when the input data is already stored as an edge list.
Both algorithms always produce an optimal MST. The choice between them depends on the density of the graph, the data representation, and the implementation goals.

In terms of theoretical complexity:

Prim’s algorithm has O(E log V) complexity.

Kruskal’s algorithm has O(E log E) complexity.

For most graphs, these are nearly equivalent since E log E is approximately equal to E log V, meaning performance differences mostly come from practical implementation rather than asymptotic behavior.

4. Implementation Notes

The program was implemented in Java (JDK 17 or later).
The Gson 2.10.1 library was used for JSON parsing.

Input file: src/main/resources/ass_3_input.json
Output file: ass_3_output.json
