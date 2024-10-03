# Linked Lists
A linked list is a collection of independent memory locations called nodes. Nodes are connected through links in a linear order. The links are usually implemented as pointers. Linked lists are sometimes an alternative to overcome some of the limitations of the typical array such as fixed length and unnecessary storage use. 

To represent the linked list, we use a pointer to the first node. This first node is called the **head** of the linked list, while the last node is called the **tail**. When the linked list is empty, the value of the head is NULL (or None in Python).

While insertion at the beginning and end of the list has a O(1) complexity, accessing to elements can have a O(n) in the worst case scenario because it is not possible to locate the elements in the nodes by index. Also, deletion at every position can take O(n) in the worst case as it is necessary to traverse the list in order to find the element to delete. It is possible to remove the head of the list in O(1).

## Member functions and attributes

* ll.push(element): Add an element at the head of the linked list (if the linked list is implemented using a stack, it will add an element to the top of the stack). 

* ll.delete(node): 

* myNode.value(): A reference to the element stored in the node

* myNode.next(): The reference to the next node in the list. myNode.next() will be NULL if the list is empty or if the myNode is the last node in the singly linked list. 

## Applications
Linked lists are used to represent filesystems (hierarchical structure of the directories), to implement another data structures such as stacks or queues, graph implementation which uses linked lists to store adjacent vertices.

## Code Implementation
For the main implementation, we will declare a Node, which will contain certain type of data, as well as a pointer (or reference) to the next node. 

### Python implementation
From the LeetCode linked list implementation to define a linked list [1, 2, 4], you write "l1 = ListNode(1,ListNode(2, ListNode(3, None)))". Hence, to get the first value (the head) of l1, we do "l1.val"; to get second value, we do "l1.next.val"; and to get the third value, we do "l1.next.next.val"

=== "Python"

    ``` py linenums="1" title="Single Linked List"
        return -1
    ```

### C++ implementation
In addition to the "from zero" implementation, we can also leverage the defined container forward_list, defined in STL. 

[^1]: Cormen, T.H. et al. (2022) Introduction to algorithms. Cambridge, MA: The MIT Press. 
[^2]: Goodrich, M.T., Tamassia, R. and Goldwasser, M.H. (2013) Data Structures and algorithms in Python. Hoboken, NJ: Wiley. 
[^3]: Skiena, S.S. (2020) The Algorithm Design Manual. 3rd edn. Springer. 
[^4]: Introduction to algorithms: Electrical Engineering and computer science MIT OpenCourseWare. Available at: https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/ (Accessed: 29 September 2024). 
[^5]: Data Structures & Algorithms - Linked Lists - Singly Linked Lists. Available at: https://youtu.be/gpvtfbwgUxM?list=PLaBPUIXZ8s4D2onKZ2wj7dUCglYfA5wBd