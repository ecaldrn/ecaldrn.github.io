# Linked Lists
A linked list is a collection of independent memory locations called nodes. Nodes are connected through links in a linear order. The links are usually implemented as pointers. Linked lists are sometimes an alternative to overcome some of the limitations of the typical array such as fixed length and unnecessary storage use. 

To represent the linked list, we use a pointer to the first node. This first node is called the **head** of the linked list, while the last node is called the **tail**. When the linked list is empty, the value of the head is NULL (or None in Python).

While insertion at the beginning and end of the list has a O(1) complexity, accessing to elements can have a O(n) in the worst case scenario because it is not possible to locate the elements in the nodes by index. Also, deletion at every position can take O(n) in the worst case as it is necessary to traverse the list in order to find the element to delete. It is possible to remove the head of the list in O(1).

## Member functions and attributes

* linked_list.push(element): Add an element at the head of the linked list (if the linked list is implemented using a stack, it will add an element to the top of the stack). 

* linked_list.delete(node): 

* myNode.value(): A reference to the element stored in the node

* myNode.next(): The reference to the next node in the list. myNode.next() will be NULL if the list is empty or if the myNode is the last node in the singly linked list. 

## Applications
Linked lists are used to represent filesystems (hierarchical structure of the directories), to implement another data structures such as stacks or queues, graph implementation which uses linked lists to store adjacent vertices.

## Code Implementation
For the main implementation, we will declare a Node, which will contain certain type of data, as well as a pointer (or reference) to the next node. 

### Python implementation
From the LeetCode linked list implementation to define a linked list [1, 2, 4], you write "l1 = ListNode(1,ListNode(2, ListNode(3, None)))". Hence, to get the first value (the head) of l1, we do "l1.val"; to get second value, we do "l1.next.val"; and to get the third value, we do "l1.next.next.val"

=== "Python"

    ``` py linenums="1" title="Singly Linked List"
    # Code from this video: https://youtu.be/dqLHTK7RuIo
    class Node:
        def __init__(self, val, next=None):
            self.val = val
            self.next = next

        def __str__(self):
            return str(self.val)

    #Traverse the singly linked list
    #curr = Head
    #while curr: #This implies while curr != None
    #    print(curr)
    #    curr = curr.next

    #Display the linked list
    def display(Head):
        curr = Head
        elements = []

        while curr:
            elements.append(curr.val)
            curr = curr.next
        
        print(" -> ".join(elements))

    # Search for a given element in the list
    def search(head, target):
        curr = head

        while curr:
            if target == curr.val:
                return True
            curr = curr.next
        
        return False

    # How to use the class
    # Create the List defined by Head -> A -> B -> C
    # Create the isolated nodes, then make the connections
    Head = Node(1)
    A = Node(3)
    B = Node (4)

    Head.next = A
    A.next = B
    B.next = C

    display(Head) # Will print 1 -> 3 -> 4
    search(Head, 2) # Will return False
    ```
    ``` py linenums="1" title="Doubly linked lists"
    class DoublyNode:
        def __init__(self, val, next=None, prev=None):
            self.val = val
            self.next = None
            self.prev = None

        def __str__(self):
            return str(self.val)

    #Display the doubly linked list
    def display(Head):
        curr = Head
        elements = []

        while curr:
            elements.append(curr.val)
            curr = curr.next
        
        print(" <-> ".join(elements))

    def insert_at_beginning(head, tail, val):
        new_node = DoublyNode(val, next=head)
        head.prev = new_node
        return new_node, tail

    def insert_at_end(head, tail, val):
        new_node = DoublyNode(val, next=tail)
        tail.prev = new_node
        return head, new_node

    # Calling the functions
    head, tail = insert_at_beginning(head, tail, 3)
    display(head)       
    ```

### C++ implementation
=== "C++"

    ``` c++ linenums="1" title="Linked list using a structure and pointers (Classic)"
    //Used code from: 
    // https://www.linkedin.com/learning/nail-your-c-plus-plus-interview
    #include <iostream>
    #include <cstdlib>
    using namespace std;

    struct Node{
    int data;
    Node *next;
    };

    void insert(struct Node** head, int newData);
    void printList(struct Node *head);
    void deleteNode(struct Node** head, int position);

    int main(){
    Node* head = NULL;

    insert(&head, 9);
    insert(&head, 1);
    insert(&head, 3);
    insert(&head, 8);

    cout << "Created " << endl;
    printList(head);
    deleteNode(&head, 3);
    cout << "\n After deletion of position 3 " << endl;
    printList(head);
    return 0;
    }

    void insert(struct Node** head, int newData){
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));

    newNode->data =  newData;
    newNode->next = *head;

    *head = newNode;
    }

    void deleteNode(struct Node** head, int position){
    if (*head == NULL) //if the list is empty, simply return
        return;
    
    struct Node* temp = *head; //create new pointer to head

    //if they want to delete head, move head to next item, delete and return
    if (position == 0){
        *head = temp->next;
        free(temp);
        return;
    }

    //cycle through list until end or node b4 position
    for (int i=0; temp!=NULL && i < position-1; i++){
        temp = temp->next;
    }

    if (temp == NULL || temp->next == NULL) ////if end of list, return
        return;
        
    //create new pointer to point to positions pointer
    struct Node *next = temp->next->next;
    //delete position
    free(temp->next);
    //unlink node
    temp->next = next;
    }

    void printList(struct Node *head){
    while (head != NULL){
        cout << head->data;
        head = head->next;
    }
    }
    ```
In addition to the "from zero" implementation, we can also leverage the defined container forward_list, defined in STL. 
=== "C++"

    ``` c++ linenums="1" title="Singly linked list using STL forward_list container"
    #include <iostream>
    #include <forward_list>
    using namespace std;

    struct node(vector<int>& nums, int target) {
    }

    ```

Finally, we have the list container, that is defines a doubly-linked list and is included in the STL C++ library. 
=== "C++"

    ``` c++ linenums="1" title="Doubly Linked list using a STL list container"
    #include <iostream>
    #include <list>
    using namespace std;

    struct node(vector<int>& nums, int target) {
    }

    ```

[^1]: Cormen, T.H. et al. (2022) Introduction to algorithms. Cambridge, MA: The MIT Press. 
[^2]: Goodrich, M.T., Tamassia, R. and Goldwasser, M.H. (2013) Data Structures and algorithms in Python. Hoboken, NJ: Wiley. 
[^3]: Skiena, S.S. (2020) The Algorithm Design Manual. 3rd edn. Springer. 
[^4]: Introduction to algorithms: Electrical Engineering and computer science MIT OpenCourseWare. Available at: https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/ (Accessed: 29 September 2024). 
[^5]: Data Structures & Algorithms - Linked Lists - Singly Linked Lists. Available at: https://youtu.be/gpvtfbwgUxM?list=PLaBPUIXZ8s4D2onKZ2wj7dUCglYfA5wBd