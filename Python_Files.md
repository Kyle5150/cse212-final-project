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
## Set Problem: Searching for Users

```python
facebook_users = {"xd35", "pdi89", "qiqq89", "htayw098", "hsyt2", "iows76", "cow45", "pkuy77", "jsiiw90", "tree33"}

instagram_users = {"htayw098", "cow45", "rewd67", "ghost7", "perky", "lot43", "kk12"}

Only_Facebook = set()

Only_Instagram = set()

for x in facebook_users:
    if x not in instagram_users:
        print(f"user: {x} is only found on Facebook\n")
        Only_Facebook.add(x)

for x in instagram_users:
    if x not in facebook_users:
        print(f"user: {x} is only found on Instagram\n")
        Only_Instagram.add(x)

Intersection = facebook_users & instagram_users
for x in Intersection:
    print(f"user: {x} is found on both Facebook and Instagram\n")

print(f"Number of only Facebook users: {len(Only_Facebook)}")

print(f"Number of only Instagram users: {len(Only_Instagram)}")

print(f"Number of both platform users: {len(Intersection)}")
```
## Tree Problem: Complete the Tree
```python
class Node:

    def __init__(self, data):

        self.left = None
        self.right = None
        self.data = data

# Insert method to create nodes
    def insert(self, data):

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

# findval method to compare the value with nodes
    def findval(self, lkpval):
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

# Print the tree
    def PrintTree(self):
        if self.left:
            self.left.PrintTree()
        print(self.data),
        if self.right:
            self.right.PrintTree()

root = Node(27)
root.insert(14)
root.insert(35)
root.insert(31)
root.insert(10)
root.insert(19)
root.PrintTree()
print(root.findval(7))
print(root.findval(14))
```
