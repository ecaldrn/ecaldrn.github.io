# Stack
A stack is a LIFO (Last In, First Out) linear structure. You can think the stack as a stack of plates in a restaurant, in which you cannot get the plate in the bottom without removing the ones that are on top. Stacks can be used as base to create another data structures. 

## Member functions and atributes

* Stack.push(element): This will add element to the top of the stack. It has a running time of O(1).

* Stack.pop(): Retrieves, removes from stack, and returns the element in the top of the stack (last element added). It has a running time of O(1).

* Stack.top(): References to the element in the top of the stack without removing it. Points to the last element added and if the stack is empty, an error arises.

* Stack.isEmpty(): Boolean attribute, indicates if the stack is empty or not. 

* len(Stack): Number of existing elements in the stack. 

## Applications
Stacks are used in a wide variety of scenarios, such as the stack that saves our operations made in some program so we can use the undo command (ctrl+z) to return to the last operation made (execute(operation_history.pop())).

Another application of stacks is seen in web browsers, which keep a record of recently visited sites wo you can move easily between visited pages.

Stacks are also used to verify matching expressions, such as opening-closing pairs of parenthesis, brackets, or even markup tags. 

## Code Implementation
For the main implementation, 

### Python implementation
=== "Python"

    ``` py linenums="1" title="Single Linked List"
        return -1
    ```

### C++ implementation
In addition to the "from zero" implementation, we can also leverage the defined container , defined in STL. 

[^1]: Cormen, T.H. et al. (2022) Introduction to algorithms. Cambridge, MA: The MIT Press. 
[^2]: Goodrich, M.T., Tamassia, R. and Goldwasser, M.H. (2013) Data Structures and algorithms in Python. Hoboken, NJ: Wiley. 
[^3]: Skiena, S.S. (2020) The Algorithm Design Manual. 3rd edn. Springer. 
[^4]: Introduction to algorithms: Electrical Engineering and computer science MIT OpenCourseWare. Available at: https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/ (Accessed: 29 September 2024). 
[^5]: Data Structures & Algorithms - Linked Lists - Singly Linked Lists. Available at: https://youtu.be/gpvtfbwgUxM?list=PLaBPUIXZ8s4D2onKZ2wj7dUCglYfA5wBd