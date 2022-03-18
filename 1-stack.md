# Stack

A stack is a data structure that stores items in a Last-In/First-Out manner. This is frequently referred to as **LIFO**. 

A stack works exactly like the *Undo* feature in Word. They keep track of what you've performed with the most recent action being kept at the top of the stack.

The built-in **list** structure that you likely use frequently in your programs can be used as a stack. Instead of .push(), you can use **.append()** to add new elements to the top of your stack, while **.pop()** removes the elements in the LIFO order:

## LIFO

This image shows the process of items (colored balls) being stored in the Last-In/First-Out method of the stack. 

![stack-LIFO-image#1](https://user-images.githubusercontent.com/77080668/159053784-22f92d19-d8cc-46b8-84e2-d08d5b895849.jpeg)

In python, this code will create a stack, add the numbers 1, 2, 3 to the stack (in that order) and then remove one of those numbers from the stack. Which number will be removed from the stack in this code?
```
my_stack = []

my_stack.append(1)
my_stack.append(2)
my_stack.append(3)

my_stack.pop()

print(my_stack)
```

The number 3 will be removed from the stack because of the LIFO process.

### Operations
| Stack Operation | Description                                 | Python                 | Big-O |
|-----------------|---------------------------------------------|------------------------|-------|
| push(value)     | Adds a "value" to the end of a stack.       | my_stack.append(value) | O(1)  |
| pop()           | Removes and returns the end item.           | item = my_stack.pop()  | O(1)  |
| size()          | Returns the size of the stack.              | length = len(my_stack) | O(1)  |
| empty()         | Returns True if the size of the stack is 0. | if len(my_stack) == 0  | O(1)  |


[Back to Welcome Page](https://github.com/Kyle5150/cse212-final-project/blob/main/0-welcome.md)
