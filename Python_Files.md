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
