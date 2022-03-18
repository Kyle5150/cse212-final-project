# Python

## Stack Problem: Shopping Cart

```python
my_stack = []

def items(item):
    my_stack.append(item)
    print(f"\n {my_stack}")

user = "0"
while user != "5":
    user = input("\n1. View Cart \n2. Add Item \n3. Remove Previous Item \n4. Number of Items \n5. Quit \nPlease enter a number: ")
    if user == "1":
        if len(my_stack) == 0:
            print("\nNothing in cart")
        else:
            print(my_stack)
    elif user == "2":
        item = input("\n Enter item: ")
        items(item)
    elif user == "3":
        my_stack.pop()
        print(f"\n {my_stack}")
    elif user == "4":
        print(f"\n{len(my_stack)}")
```
