# Stacks and Queues
[Home](../README.md)  
[Source](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)  

## Stack
* Stacks are useful in understanding  of how interpreter works 
* we see examples of it during the call stack, in recursive functions, and with interpreter
* we are limited by the RAM available for multiple stacks causing stack overflow.
* Push - BigO(1)  
* Pop - BigO(1)  
* Peek - BigO(1)  
* IsEmpty - BigO(1)  
* Linked List with limitations that are deliberatly introduced so that we can take advantage of the BigO(1)  

## Queue  
* There are many types of queues. Most common is priority queue. 
* Linked lists and list do not work with Queue without making them in BigO(1)  
* __Using deques this is faster__:       
    > from collections import deque
    > class Queue():  
    >   def __init__(self):  
    >     self.storage = deque()  
    >   def enqueue(self,item):  
    >     self.storage.appendleft(item)  
    >   def dequeue(self):  
    >     return self.storage.pop()  
    >   def peek(self):
    >     return self.storage[-1]  
    >   def is_empty(self):  
    >     return len(self.storage)==0  


