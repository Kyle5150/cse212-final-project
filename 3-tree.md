# Tree

The **tree** data structure is a unique data structure in which data items are connected using references in a hierarchical manner. A tree consists of a root node and a combination of internal nodes (also known as vertices) and edges. A node is where we store data, and an edge is a path between two nodes.

In python, a process called **recursion** is used when dealing with trees. Recursion is the process of defining something in terms of itself. A real world example would be to place two parallel mirrors facing each other. Any object in between them would be reflected recursively.

A tree whose elements have at most two children is called a **binary tree**. Each element in a binary tree can have only two children.

A **binary search tree**, or BST for short, is a tree whose nodes store a key that is greater than all of their left child nodes and less than all of their right child nodes. Binary trees are useful for storing data in an organized manner so that it can be quickly retrieved, inserted, updated, and deleted.

## Recursion

Recursion is a technique where a function calls itself.

This is an example of a recursive function.
```python
def recurse():
  recurse()
recurse()
```
This function will call the 'recurse()' function forever.

To properly use recursion, there are two rules to always follow:
1. Smaller Problem
- When using recursion, you need to make sure to call the function on a smaller problem. Without this rule, our function will run forever.
2. Base Case
- As you continue to call the function on a smaller problem, there needs to be a stopping point. You must define a scenario in which recursion is not required. This is called the base case.

Applying these two rules to our previous code example, you can begin to see the benefits of using recursion:
```python
def recurse(count):
  if count <= 0:  # Base Case
	return
  else:
	print("Recursing")
	recurse(count-1)  # Smaller Problem
```
The smaller problem is 'count-1' and the base case is when 'count' is equal (or less than) zero.

### Memoization

**Memoization** is the process of remembering previous results so that additional recursive calls are not needed. For more complicated problems that would require extremem amounts of recursive calls, memoization comes in handy. Think of memoization as a bookmark in an operation of code.

We can implement memoization by simply creating a dictionary that remembers certain curicial spots in a recursive function.
```python
if remember is None:
	remember = dict()

# Base Case
if n <= 2:
	return 1

# Check if we have solved this one before
if n in remember:
	return remember[n]
```
This is not a full/functional code example, but this is what memoization would look like in a possible soluion.

Depending on how efficient a recursive function is, the performance of a recursive algorithm can, at best, be O(log n) through memoization.

## Binary Trees

A tree whose elements have at most two children is called a **binary tree**. Each element in a binary tree can have only two children. A node’s left child must have a value less than its parent’s value, and the node’s right child must have a value greater than its parent value.

![tree-Binary-Tree-image#1](https://user-images.githubusercontent.com/77080668/161633458-6e559510-96a9-4012-b195-198ae1e90c69.png)

- Node: Each element (number) is a node in the image above.
- Root: The root is the first node that creates the tree, in this instance, node #8 is the root.
- Leaf: The nodes that connect to no other nodes are called leaves (1, 4, 7, 13).
- Parent: A node that has connected nodes is called a parent.
- Child: The node connected to the parent is called a child.
- Subtree: The nodes to the left and right of any parent node form a subtree.

## Binary Search Tree (BST)

A ***binary search tree (BST)*** is a binary tree that follows rules for data that is put into the tree. Data is placed into the BST by comparing the data with the value in the parent node. If the data being added is less than the parent node, then it is put in the left subtree. If the data being added is greater than the parent node, then it is put in the right subtree.

This code will create the beginnings of a tree ny using a 'Node' class and giving the root node a value of 27:
```python
# node class
class Node:

    def __init__(self, data):
        # left child
        self.left = None
        # right child
        self.right = None
        # node's value
        self.data = data

    # print function
    def PrintTree(self):
        print(self.data)

root = Node(27)

root.PrintTree()
```

## BST Operations

### Inserting

This block of code is an example function that inserts new data into the tree by comparin the new value with the parent node:
```python
def insert(self, data):
# Compare the new value with the parent node
	if self.data:
	    if data < self.data:
		if self.left is None:
		    self.left = Node(data)
		else:
		    self.left.insert(data)
	    elif data > self.data:
		if self.right is None:
		    self.right = Node(data)
		else:
		    self.right.insert(data)
	else:
	    self.data = data
```

### Traversing

This block of code is an example function that finds if a value is in the tree by comparing it with each node:
```python
def findval(self, lkpval):
# findval method to compare the value with nodes
	if lkpval < self.data:
	    if self.left is None:
		return str(lkpval)+" is not Found"
	    return self.left.findval(lkpval)
	elif lkpval > self.data:
	    if self.right is None:
		return str(lkpval)+" is not Found"
	    return self.right.findval(lkpval)
	else:
	    return str(self.data) + " is found"
```

Common BST Operation | Description                                   | Performance
---------------------|-----------------------------------------------|--------------
insert(value)        | Insert a value into the tree.                 | O(log n) - Recursively search the subtrees to find the next available spot.
remove(value)        | Remove a value from the tree.                 | O(log n) - Recursively search the subtrees to find the value and then remove it.                        |                                               |            This will require some cleanup of the adjacent nodes.
contains(value)      | Determine if a value is in the tree.          | O(log n) - Recursively search the subtrees to find the value.
traverse_forward     | Visit all objects from smallest to largest.   | O(n) - Recursively traverse the left subtree and then the right subtree.
traverse_reverse     | Visit all objects from largest to smallest.   | O(n) - Recursively traverse the right subtree and then the left subtree.
size()               | Return the size of the BST.                   | O(1) - The size is maintained within the BST class.
empty()              | Returns true if the root node is empty.       | O(1) - The comparison of the root node or the size.

## Example: Tree

Here is an example of a tree that can be inserted into. Use this code to complete the **Problem to Solve**.
```python
class Node:

    def __init__(self, data):

        self.left = None
        self.right = None
        self.data = data

    def insert(self, data):
# Compare the new value with the parent node
        if self.data:
            if data < self.data:
                if self.left is None:
                    self.left = Node(data)
                else:
                    self.left.insert(data)
            elif data > self.data:
                if self.right is None:
                    self.right = Node(data)
                else:
                    self.right.insert(data)
        else:
            self.data = data

# Print the tree
    def PrintTree(self):
        if self.left:
            self.left.PrintTree()
        print(self.data),
        if self.right:
            self.right.PrintTree()

# Use the insert method to add nodes
root = Node(27)
root.insert(14)
root.insert(35)
root.insert(31)
root.insert(10)
root.insert(19)

root.PrintTree()
```

## Problem to Solve: Complete the Tree

Now it is your turn! Use this starting code to complete your own tree that can perform the following:

1. insert into tree
2. traverse tree to find values
3. print full tree

Try to do as much as you can without looking at any other code.

* Remember there is never simply one solution!

[Back to Welcome Page](https://github.com/Kyle5150/cse212-final-project/blob/main/0-welcome.md)
