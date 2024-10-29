# Reverse a linked list


**Input** 

1. .
1. .

**Output**: 1

**Time complexity**: O()

**Space complexity**: O

=== "C++"

    ``` c++ linenums="1" title="Reverse a Linked List in C++"
    #include <vector>

    int search(vector<int>& nums, int target) {
    }
    ```

=== "Python"

    ``` py linenums="1" title="Reverse a Linked List in Python"
    # Definition for singly-linked list.
    class ListNode:
        def __init__(self, val=0, next=None):
            self.val = val
            self.next = next

    # Input: head of a linked list
    # Output: Return the reversed list.
    # Time O(n)
    # Space O(1)

    class Solution:
        def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
            current = head
            prev = None

            while (current):
                tmp = current.next # Keeps the list from current.next till the end
                current.next = prev # Change the orientation of the nodes links (reverses the connections)
                prev = current # Moves in to the next node
                current = tmp
                
            return prev
    ```