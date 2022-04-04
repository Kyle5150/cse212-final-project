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

![tree-Binary-Tree-image#1](https://user-images.githubusercontent.com/77080668/161633147-daa438eb-bb82-424d-a455-3b308647a7e7.png)

## Binary Search Tree (BST)

## BST Operations

## Example: 

## Problem to Solve: Complete the Tree

* Remember there is never simply one solution!

[Back to Welcome Page](https://github.com/Kyle5150/cse212-final-project/blob/main/0-welcome.md)
