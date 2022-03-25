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

### Common Set Operations

| Set Operation   | Description                                 | Python                 | Big-O |
|-----------------|---------------------------------------------|------------------------|-------|
| add(value)      | Adds a "value" to the set.                  | my_set.add(value)      | O(1)  |
| remove(value)   | Removes the specific "value" from the set.  | my_set.remove(value)   | O(1)  |
| member(value)   | Checks membership of a "value" in the set.  | if value in my_set:    | O(1)  |
| size()          | Returns the number of items in the set.     | length = len(my_set)   | O(1)  |

### Mathematical Operations

1. Intersection
2. Union

When comparing values between two sets, Python has built in methods of finding similar values in multiple sets and combining multiple sets.

This code shows both the intersection (&) of set_1 and set_2, and the union (|) of them.
```python
set_1 = {1, 2, 3, 4, 5}
set_2 = {4, 5, 6, 7, 8}

similar = set_1 & set_2
combo = set_1 | set_2

print(similar)
print(combo)
```
```python
Output: {4, 5}
        {1, 2, 3, 4, 5, 6, 7, 8}
```

## Hashing

If we used the value we wanted to add to our set to determine the index into the list, we might be able to achieve O(1). Consider the function index(n) = n. This would work for small amounts of data per set, however, if we were working with billions od data values, this index(n) = n function would not be efficient enough.

This is where the modula (%) operator is used behind the scenes when sets are being used. Using this equation: index(n) = n % 10 we can now store values in the hundreds of millions. 

This image shows the process of index(n) = n % 10:

![set-Hashing-image#1](https://user-images.githubusercontent.com/77080668/160170950-d9cc6164-e595-449d-a4d8-3268a78a7706.png)

The 'Hash Table' represents the set, and the 'List' represents the values being inputted into the set.

The equations mentioned earlier can be generalized into the equation: index(n) = n % sparse_list_size. This works great for numbers and can also be used for string values by using the **hashing function** - hash(n). The hashing function converts non-integers into integers so that the modulo operation can be used. 

```python
hash(6)
hash(-5)
hash("car")
hash(True)
```
```python
Output: 6
        -5
        1884511358876639000
        1
```
String values returned by the hash function will vary every time you run the code, but they will be consistent while you are running the code to completion.

## Solving Conflicts

The possiblity of having an index already occupied in a set (especially with big sets of data) is possible. There are two main ways of resolving conflicts within sets:

1. Open Addressing

If we use our index(n) hashing function and find that something already occupies the space (or the item in that space is not what we are looking for), then the open addressing strategy moves to the next available space. The simplest way this is done is by moving to the next available space to the right. However, this approach is that a conflict can result in the creation of more conflicts.

3. Chaining

Instead of looking for a new place for our data, we can make a list of values that are held in the same space/index. Think of chaining like adding multiple files into a folder being held in a cabinet of folders.

Using these conflict resolving strategies helps us keep the O(1) performace with sets.

## Example: 

## Problem to Solve: Searching for Users

Write a program (utilizing sets) that prints where each user is found, either on Facebook, Instagram, or both. Then print the number of users only on Facebook, only on Instagram, and number of users on both platforms.

Use these two sets to write this program:
```python
facebook_users = {"xd35", "pdi89", "qiqq89", "htayw098", "hsyt2", "iows76", "cow45", "pkuy77", "jsiiw90", "tree33"}

instagram_users = {"htayw098", "cow45", "rewd67", "ghost7", "perky", "lot43", "kk12"}
```

Remember these notes as you create your program:
1. To create an empty set: my_set = set()
2. Keywords: 'in' and 'not in'
3. Intersection and Union might come in handy.

You can check your code with the solution here: [Solution](https://github.com/Kyle5150/cse212-final-project/blob/main/Python_Files.md#set-problem-searching-for-users)

[Back to Welcome Page](https://github.com/Kyle5150/cse212-final-project/blob/main/0-welcome.md)
