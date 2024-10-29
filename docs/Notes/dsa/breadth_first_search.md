# Breadth-First Search
This approach of traversing a graph will give you the shortest path to a given node. 


## Main applications
* Flight reservation systems
* GPS
* Many social networks uses BFS to map your friend/connection suggestions. 
* Web crawlers
* Flood fill (The bucket-fill function in Paint program). 

**Time complexity**: O(V + E) where V is the number of vertices of the graph, while E is the number of edges.

**Space complexity**: 

=== "C++"

    ``` c++ linenums="1" title="BFS in C++"
    #include <vector>

    int dfs(vector<int>& nums, int target) {

        return -1;
    }
    ```

=== "Python"

    ``` py linenums="1" title="BFS iterative approach"
    # We will use a queue to keep track of nodes to visit
    marked = [False] * graph.size()

    def bfs_iter(graph, v):
        queue = [v]
        while len(queue) > 0: #As long as we have nodes to visit
            v = stack.pop()

            if not marked[v]:
                visit(v)
                marked[v] = True

                for w in graph.neighbors(v):
                    if not marked[w]:
                        queue.enqueue(w)
    ```

Useful resource https://youtu.be/xlVX7dXLS64