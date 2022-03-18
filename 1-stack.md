# Stack

A stack is a data structure that stores items in a Last-In/First-Out manner. This is frequently referred to as **LIFO**. 

A stack works exactly like the *Undo* feature in Word. They keep track of what you've performed with the most recent action being kept at the top of the stack.

The built-in **list** structure that you likely use frequently in your programs can be used as a stack. Instead of .push(), you can use **.append()** to add new elements to the top of your stack, while **.pop()** removes the elements in the LIFO order:

## LIFO

Think of a stack in python as a pringles can. You can only take the chip that was last inserted into the can. This image shows the process of items (colored balls) being stored in the Last-In/First-Out method of the stack like a pringles can.

![stack-LIFO-image#1](https://user-images.githubusercontent.com/77080668/159053784-22f92d19-d8cc-46b8-84e2-d08d5b895849.jpeg)

In python, this code will create a stack, add the numbers 1, 2, 3 to the stack (in that order) and then remove one of those numbers from the stack. Which number will be removed from the stack in this code?
```python
my_stack = []

my_stack.append(1)
my_stack.append(2)
my_stack.append(3)

my_stack.pop()

print(my_stack)
```

The number 3 will be removed from the stack because of the LIFO process.

## Undo

In word, the *Undo* feature works exactly like a stack. This image shows as if you've pressed the undo button in a word document and the last command you did was indent a comment. Now, if you press the undo button again, the word you deleted would be returned, and so on.

![stack-Undo-image#2](https://user-images.githubusercontent.com/77080668/159061344-ef21cf40-5e74-4ef1-b443-1c2ace8afb98.png)

### Operations
| Stack Operation | Description                                 | Python                 | Big-O |
|-----------------|---------------------------------------------|------------------------|-------|
| push(value)     | Adds a "value" to the end of a stack.       | my_stack.append(value) | O(1)  |
| pop()           | Removes and returns the end item.           | item = my_stack.pop()  | O(1)  |
| size()          | Returns the size of the stack.              | length = len(my_stack) | O(1)  |
| empty()         | Returns True if the size of the stack is 0. | if len(my_stack) == 0  | O(1)  |

## Example: Memory

In this example, imagine you are playing a game that allows your character to move in one of four directions at a time, and a stack records your movements every action you perform. You have the options to view your previous actions, add more actions, and undo actions. This example shows exactly how the stack data structure works.

Review this code and use it as help for the Problem to Solve.

```python
my_stack = []

def movements(action):
    my_stack.append(action)
    print(f"\n {my_stack}")

user = "0"
while user != "4":
    user = input("\n1. View Memory \n2. Add Action \n3. Undo Action \n4. Quit \nPlease enter a number: ")
    if user == "1":
        if len(my_stack) == 0:
            print("\nNothing in memory")
        else:
            print(my_stack)
    elif user == "2":
        action = input("\nF (forward), B (backward), L (left), R (right): ")
        if action == "F":
            movements(action)
        elif action == "B":
            movements(action)
        elif action == "L":
            movements(action)
        elif action == "R":
            movements(action)
    elif user == "3":
        my_stack.pop()
        print(f"\n {my_stack}")
```

## Problem to Solve: Shopping Cart

Write a program that creates a shopping cart of items with additional features:

- view the shopping cart
- returns the size of the cart
- undo the last item entered

You can test your program with the following scenarios (done in order):

1. add apple, cereal, and bread to the cart: ["apple", "cereal", "bread"]
2. remove the last two items entered: ["apple"]
3. return the size of the cart: 1

You can check your code with the solution here: [Solution](https://github.com/Kyle5150/cse212-final-project/blob/main/Python_Files.md#stack-problem-shopping-cart)

[Back to Welcome Page](https://github.com/Kyle5150/cse212-final-project/blob/main/0-welcome.md)
