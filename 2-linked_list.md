# Linked Lists

Linked lists are an important data structure that are often used in projects. This tutorial will help to teach you about linked lists and how to use them.


## Basic Lists

The basic list is categorized by a specific portion of data set apart for the list. Often with larger lists it can be hard to add or remove from the middle or even the front. 
Basic lists also are limited to the size you specify in the begining. Although these often work well, there are times when you will need something else.

## Linked Lists

a linked list uses a pointer system, each value points to the value before it and the value after it. This makes it so that it is easier to add and remove from any position. It also makes it so that the list can always be added to because there is no set length. 


## Inserting/Removing with a Linked List

To insert to a linked list you have to take your last value and point it to your new value, then you need to take the new value and point it to the previous value and the next value, or the very first value.


## linked Lists With Python


## Example 1 

```python
class LinkedList:
    class Node:
        def __init__(self, data):
            self.data = data
            self.next = None
            self.prev = None

    def __init__(self):
        self.head = None
        self.tail = None

    def insert_head(self, value):
        # Create the new node
        new_node = LinkedList.Node(value)  
        
        # If the list is empty, then point both head and tail
        # to the new node.
        if self.head is None:
            self.head = new_node
            self.tail = new_node
        # If the list is not empty, then only self.head will be
        # affected.
        else:
            new_node.next = self.head # Connect new node to the previous head
            self.head.prev = new_node # Connect the previous head to the new node
            self.head = new_node      # Update the head to point to the new node
```

## Problem 1

The code above has the basics of a linked list. It has a function to add a node to the head, or the front.
Using the example make a function called insert_tail() that will insert at the tail.

Use the test code below to test your function. 
```python
ll = LinkedList()
ll.insert_head(1)
ll.insert_head(2)
ll.insert_head(2)
ll.insert_head(3)
ll.insert_head(4)
ll.insert_head(5)
print(ll) # linkedlist[5, 4, 3, 2, 2, 1]
ll.insert_tail(0)
ll.insert_tail(-1)
print(ll) # linkedlist[5, 4, 3, 2, 2, 1, 0, -1]
```

Remember to have the example code in your program or it may not work.

### Problem 1 Solution

```python
def insert_tail(self, value):
        # Create the new node
        new_node = LinkedList.Node(value) 

        # If the list is empty, then point both head and tail
        # to the new node.
        if self.head is None:
            self.head = new_node
            self.tail = new_node

        else:
            # Set up link between the old tail and the new node
            new_node.prev = self.tail
            self.tail.next = new_node
            # Change the tail to be the new node
            self.tail = new_node
```

## Example 2

The code below shows a function to remove the first item in a linked list

```python
def remove_head(self):
        """ 
        Remove the first node (i.e. the head) of the linked list.
        """
        # If the list has only one item in it, then set head and tail 
        # to None resulting in an empty list.
        if self.head == self.tail:
            self.head = None
            self.tail = None
        # If the list has more than one item in it, then only self.head
        # will be affected.
        elif self.head is not None:
            self.head.next.prev = None  # Disconnect the second node from the first node
            self.head = self.head.next  # Update the head to point to the second node
```

## Problem 2

Use the code above to help in making the code to remove the last item in the linked list. Call the new function remove_tail()
Below is some test code to help you test your solution.
```python
ll.remove_tail()
print(ll) # linkedlist[5, 4, 3, 2, 2, 1, 0]
ll.remove_tail()
print(ll) # linkedlist[5, 4, 3, 2, 2, 1]
```

Remember to use your code from problem 1

### Problem 2 Solution

```python
def remove_tail(self):
        # If the list has only one item in it, then set head and tail 
        # to None resulting in an empty list.
        if self.head == self.tail:
            self.head = None
            self.tail = None

        elif self.tail is not None:
            self.tail.prev.next = None  # Disconnect the second to last node from the last node
            self.tail = self.tail.prev  # Update the tail to point to the second to last node
```
