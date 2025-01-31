# Queue
A queue is a FIFO (First In, First Out) linear structure. You can think this data structure as a queue in the supermarket cashier, in which the first person that lines up, is the first person to be served. In a queue, the elements are inserted from the "back" (at the end of the structure) and are removed from the front (the start of the structure).

## Member functions and atributes

* queue.enqueue(element): Add the element to the back of the Queue. This method has a O(1) complexity.

* queue.dequeue(): Retrieves, removes from queue, and returns the element at the front of the queue. This method has a O(1) complexity.

* queue.first(): Returns a reference to the element at the front of the Queue (first element, 0 index). This method has a O(1) complexity.

* queue.is_empty(): Returns True if queue is there are no elements in queue. 

* len(queue): Returns the number of elements of the queue. 

## Applications
Queues are applied to web server requests management, process management in operative systems-job scheduling, as a base of very important algorithms such as Breadth-First search (BFS), song queue in music players and apps, printer queues, etc.  

## Code Implementation
For the main implementation, we decided to use deque over List because list would be slow in the inserts or pops from the beginning of the list, as we would have to shift all the elements one position (O(n)). 
Also, we are considering 0th position (left) as the head of the queue and (n-1) position (right) as the tail of our queue. 

### Python implementation
=== "Python"

    ``` py linenums="1" title="Queue implementation using Deque"
        from collections import deque

        class Queue:
            def __init__(self):
                self.items = deque()

            def is_empty(self):
                return not self.items #Same as len(self.items) == 0
            
            def enqueue(self, item):
                self.items.append(item)

            def dequeue(self):
                return self.items.popleft()
            
            def peek(self):
                return self.items[0] #Item of the head of the queue
            
            def size(self):
                return len(self.items)
            
            def __str__(self):
                return str(self.items)
    ```

### C++ implementation
In addition to the "from zero" implementation, we can also leverage the defined container , defined in STL. 

[^1]: Cormen, T.H. et al. (2022) Introduction to algorithms. Cambridge, MA: The MIT Press. 
[^2]: Goodrich, M.T., Tamassia, R. and Goldwasser, M.H. (2013) Data Structures and algorithms in Python. Hoboken, NJ: Wiley. 
[^3]: Skiena, S.S. (2020) The Algorithm Design Manual. 3rd edn. Springer. 
[^4]: Introduction to algorithms: Electrical Engineering and computer science MIT OpenCourseWare. Available at: https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/ (Accessed: 29 September 2024). 
[^5]: Data Structures & Algorithms - Linked Lists - Singly Linked Lists. Available at: https://youtu.be/gpvtfbwgUxM?list=PLaBPUIXZ8s4D2onKZ2wj7dUCglYfA5wBd