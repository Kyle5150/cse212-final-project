# Set
Unlike a stack, the set data structure does not operate based on the location of each item within. Order does not matter in a set. It is created by using curly braces (my_set = {1, 2, 3}) in python.

Sets also do not allow duplicate values within them. With the use of **hashing**, the set data structure can add, remove, and check for values being present in the set more efficiently than any other data structure.

Using the set data structure can raise some issues when dealing with filled spots within the set. Techniques such as **open addressing** and **chaining** solve these conflicts:

## Order and Operations

A set is a data structure in Python with an unordered and unindexed collection of elements. This allows for very efficient testing of membership of values in a set, which is the most important operation belonging to this data structure. 

This python code shows a set being created with curly braces and being printed out.
```python
my_set = {1, 3, 2, 8, 9, 2, 1}

print(my_set)
```
Knowing that sets don't operate based on order and don't allow duplicates, what would the output of this previous block of code be?
```python
Output: {1, 2, 3, 8, 9}
```
The numbers 1 and 2 are contained in the originally created set. When printed out, only unique values are returned, and not in numerical order. This works the same with string values in sets, which we will get to later.

### Operations



## Hashing and Efficiency

## Solving Conflicts

[Back to Welcome Page](https://github.com/Kyle5150/cse212-final-project/blob/main/0-welcome.md)
