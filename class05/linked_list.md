# Linked Lists


## Terminology: 
__Linked List__ -   
A data structure that contains nodes that links/points to the next node in the list.  
__Singly__ - Singly refers to the number of references the node has.  
__Doubly__ - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.  
__Node__ - Each node contains the data for each link.
__Next__ - Each node contains a property called Next. This property contains the reference to the next node.  
__Head__ - The Head is a reference type of type Node to the first node in a linked list.  
__Current__ - The Current reference is a reference type of type Node that is currently being looked at. 

[Reference](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)

-----

## Insertions  
* Factor in the BigO when thinking about this. 
* When inserting at the head, the new node has to link to the current node and then the head will link to it. Since it is indepedent of the size of the linked lists, the tiem and space factor is O(1)

* But when linking to the end of the list, you have to traverse through the entire breadth of the linked lists. Since this can vary based on the size, the time factor is O(n)  

* When adding to the end of the list, the new node has to connect to null first. Now there are two nodes connect to null. The the current node with the next value has null, will then attach to the new node and make it part of the linked chain.

* When adding a new node to the middle of the list, use a while loop to loop through the linked lists until you reach the node with next value as the value we want to AddBefore. Then connect the new node to the next node, and then change the current node's next value to the new node. This will insert the new node into the link. Since it is dependent on the length of the link, the BigO is O(n)

![Adding to Linked Lists](https://miro.medium.com/max/1400/1*Jy5tjwrMdtpGl2ceq4f94A.jpeg)  
[Reference](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)


![Arrays vs Linked Lists](https://miro.medium.com/max/1400/1*cUehR5S18XSoVLaPNfNzlA.jpeg)  
[Reference](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)