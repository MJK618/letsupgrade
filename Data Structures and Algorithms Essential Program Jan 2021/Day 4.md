# Linked List Construction

```
class DoublyLinkedList:
    """Linked List with Two Pointers"""

    def __init__(self):
        self.head = None
        self.tail = None
        
    # O(1) time || O(1) Space
    def setHead(self, node):
        if self.head is None:
            self.head = node
            self.tail = node
            return
         self.insertBefore(self.head, node)   

    # O(1) time || O(1) Space
    def setTail(self, node):
        if self.tail is None:
            self.setHead(node)
            return
        self.insertAfter(self.tail, node)    

    # O(1) time || O(1) Space
    def insertBefore(self, node, nodeToInsert):
        """Will insert a node before the given node"""
        if nodeToInsert == self.head and nodeToInsert.tail == self.tail:
            return 
        self.remove(nodeToInsert)    
        nodeToInsert.prev = node.prev
        nodeToInsert.next = node
        if node.prev is None:
            self.head = nodeToInsert
        else:
            node.prev.next = nodeToInsert
        node.prev = nodeToInsert        

    # O(1) time || O(1) Space
    def insertAfter(self, node, nodeToInsert):
        """Will insert a node after the given node"""
        if nodeToInsert == self.head and nodeToInsert.tail == self.tail:
            return 
        self.remove(nodeToInsert)    
        nodeToInsert.prev = node
        nodeToInsert.next = node.next
        if node.next is None:
            self.tail = nodeToInsert
        else:
            node.next.prev = nodeToInsert
        node.next = nodeToInsert    
```
# Question 1
```
    # O(p) time || O(1) Space
    def insert_any(self, position, nodeToInsert):
        """Will insert node at specified position using already defined methods"""
        if position == 1:
            self.setHead(nodeToInsert)
            return
        node = self.head
        currentPosition = 1
        while node is not None and currentPosition != position:
            node = node.next
            currentPosition += 1
        if node is not None:
            self.insertBefore(node, nodeToInsert)
        else:
            self.setTail(nodeToInsert)    
```
# Question 2
```
    # O(n) time || O(1) Space
    def delete_beg((self, self.head):
        """Takes in value of node and removes it """
        node = self.head
        while node is not None:
            nodeToRemove = node
            node = node.next
            if nodeToRemove.value == value:
                self.remove(nodeToRemove)
   ```
   
   # Question 3
   ```
    def delete_end((self, self.tail):
      """Takes in value of node and removes it """
      node = self.head
      while node is not None:
          nodeToRemove = node
          node = node.next
          if nodeToRemove.value == value:
              self.remove(nodeToRemove)
```
```
    # O(1) time || O(1) Space        
    def remove(self, node):
        """Remove the node itslef fiven it is there"""
        #Checking head or tail cases
        if node == self.head:
            self.head = self.head.next
        if node == self.tail:
            self.tail = self.tail.prev

        #Remove bindings of the passed node
        self.removeNodeBindings(node)    

    # O(n) time || O(1) Space
    def containsNodeWithValue(self, value):
        """Checks if node is there or not"""
        node = self.head
        while node is not None and node.value != value:
            node = node.next
        return node is not None    

    def removeNodeBindings(self, node):
        """Helper function for remove method, will remove bindings of the passed node"""
        if node.prev is not None:
            node.prev.next = node.next
        if node.next is not None:
            node.next.prev = node.prev
        node.next = None    
        node.prev = None    

```
# Question 4
There's no guarantee that beg+end is representable; but in the second case the intermediate values, as well as the expected result, are no larger than end, so there is no danger of overflow.

# Question 5
```
#include <stdio.h>

// Function to perform Ternary Search
int ternarySearch(int l, int r, int key, int ar[])
{
	if (r >= l) {

		// Find the mid1 and mid2
		int mid1 = l + (r - l) / 3;
		int mid2 = r - (r - l) / 3;

		// Check if key is present at any mid
		if (ar[mid1] == key) {
			return mid1;
		}
		if (ar[mid2] == key) {
			return mid2;
		}
		if (key < ar[mid1]) {

			// The key lies in between l and mid1
			return ternarySearch(l, mid1 - 1, key, ar);
		}
		else if (key > ar[mid2]) {

			// The key lies in between mid2 and r
			return ternarySearch(mid2 + 1, r, key, ar);
		}
		else {

			// The key lies in between mid1 and mid2
			return ternarySearch(mid1 + 1, mid2 - 1, key, ar);
		}
	}

	// Key not found
	return -1;
}
