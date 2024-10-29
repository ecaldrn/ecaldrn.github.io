# Depth-First Search
What a **graph traversal** means ? From a arbitrary start node, being able to get to every other vertex in the graph. An algorithm to visit every vertex of a graph. Many of the graph traversal algorithms are different by the order in which they visit vertices. 

As we will continue on a particular path until either it finds its goal or reaches a dead end, it is considered an agressive algorithm. DFS is better in situations in which the goal is to discover a path to a given destination as soon as possible, even though this path could not always be the shortest one.

## Main applications
* Criteria-based optimizations: It can be cost, speed, safety, fuel,etc. depending on your application. 
* Pathfinding
* Maze generation
* Scheduling algorithms
* Determining the order of compilation tasks for software builds.
* Data serialization
* Resolving symbol dependencies.
* Simulation of some games.

We have a recursive and iterative approaches for DFS, and even though they both have the same runtime, most of the times the recursive approach is more used given that is cleaner and easier to read. We also have preorder (we add the node as soon as we checked that it was not in the visited list) and posorder (we add the node until it is a dead-end = we visited all the neighbor nodes) traversal arrangements. 

**Time complexity**: O(V + E) where V is the number of vertices of the graph, while E is the number of edges.

**Space complexity**: 

=== "C++"

    ``` c++ linenums="1" title="Depth-First Search in C++"
    #include <vector>

    int dfs(vector<int>& nums, int target) {

        return -1;
    }
    ```

=== "Python"

    ``` py linenums="1" title="DFS recursive approach"
    # Graphs are represented using adjacency lists
    marked = [False] * graph.size() # List used to mark visited nodes

    def dfs(graph, v):
        visit(v) 
        marked[v] = True

        for w in graph.neighbors(v):
            if not marked[w]:
                dfs(graph, w)
    ```
    ``` py linenums="2" title="DFS iterative approach"
    # We will use a stack to keep track of nodes to visit
    marked = [False] * graph.size()

    def dfs_iter(graph, v):
        stack = [v]
        while len(stack) > 0: #As long as we have nodes to visit
            v = stack.pop()

            if not marked[v]:
                visit(v)
                marked[v] = True

                for w in graph.neighbors(v):
                    if not marked[w]:
                        stack.push(w)
    ```

Useful resource https://youtu.be/PMMc4VsIacU