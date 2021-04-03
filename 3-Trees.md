# Trees
Trees are similar to linked lists in that they have nodes that point to eachother. the difference comes in how they point to eachother. Where a linked list forms a continuous line each node only pointing to the item before and after it, a tree can point to numerous nodes, and often doesn't point back. 

## Tree Basics
with trees you have a root. From that root you can get to any other node in the tree. 
Below is an example of a tree

![](https://github.com/PainBro/Winter_2021_Data_Structure_Tutorial/blob/main/Tree.png)

You can see in the tree that there is a parent and child nodes. Any node that points to another is the parent to the other and the one it points to is a child to it.

### Binary Search Tree
a binary search tree uses a pattern or system to easily place and find items. For example if we had a tree organised by number and a root of 50. if we want to find the number 30 we can know to take the left branch which goes towards the lower numbers.

### Ballanced Binary Search Tree
a balanced binary search will right itself to make each side relatively even. for instance if we had a tree with numbers 1-10 the root would be 5. say we want to change it to numbers 1-50. It would automatically change itself to have the roots closer to 25.

## Example 1 
Below is the beginning to a binary search tree class

```python
class BST:
    class Node:
        def __init__(self, data):
       
            self.data = data
            self.left = None
            self.right = None

    def __init__(self):
        self.root = None

    def insert(self, data):
        if self.root is None:
            self.root = BST.Node(data)
        else:
            self._insert(data, self.root)  # Start at the root
```

## Problem 1
For this problem you will use the code in example 1 and add to the insert function.
in the example is the first half of the function which will handle the left side.
Add code to work if the insert is on the right.


### Problem 1 Solution
put this into the insert function.
```python
if data < node.data:
            # The data belongs on the left side.
            if node.left is None:
                # We found an empty spot
                node.left = BST.Node(data)
            else:
                # Need to keep looking.  Call _insert
                # recursively on the left sub-tree.
                self._insert(data, node.left)
        elif data > node.data:
            # The data belongs on the right side.
            if node.right is None:
                # We found an empty spot
                node.right = BST.Node(data)
            else:
                # Need to keep looking.  Call _insert
                # recursively on the right sub-tree.
                self._insert(data, node.right)
```

## Example 2
Here is a function to iterate through the tree
```python
  def __iter__(self):
        yield from self._traverse_forward(self.root)  # Start at the root
        
  def _traverse_forward(self, node):
        if node is not None:
            yield from self._traverse_forward(node.left)
            yield node.data
            yield from self._traverse_forward(node.right)
```

## Problem 2
Using the example above and this starter code below create a function to iterate backwards.
```python
  def __reversed__(self):    
        yield from self._traverse_backward(self.root)  # Start at the root
```

### Problem 2 Solution
```python
def _traverse_backward(self, node):
        # same as forward, but swapped
        if node is not None:
            yield from self._traverse_backward(node.right)
            yield node.data
            yield from self._traverse_backward(node.left)
```
