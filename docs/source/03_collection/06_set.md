# Set in Python

A set is a container of an unordered collection of 'unique' and immutable objects. A set is un-indexed, therefore, 
they do not support functions including slicing, indexing and any other function that is associated with sequencing.

Sets are used to store multiple items in a single variable.  Sets are a collection of data with no duplicates. 
They are very useful when it comes to removing duplicate data from data collections.

Python sets can have different items of different data types such as float, integer, string or even tuple. 
Python set elements cannot be changed but can only be added or updated

## Creating Set

In Python, sets are written with curly brackets or using the built-in Python function `set()`.

```py
vlan_num = {10, 20, 30, 40, 50}
print(vlan_num)
```

```console
{50, 20, 40, 10, 30}
```

When we `print()` the set, duplicates were removed automatically.

```py
vlan_name = {"tech", "accounts", "guest", "tech"}
print(vlan_name)
```

```console
{'guest', 'accounts', 'tech'}
```

It is also possible to use the `set()` constructor to make a set.

```py
vlan_name = set(("tech", "guest", "accounts"))
print(vlan_name)
```

```console
{'accounts', 'guest', 'tech'}
```

## Set Method

In set, we can’t change a value. However, we can add, remove etc.

### Adding items

There are two ways to add items to a set:

- add()
- update()

```py
vlan_num = {10,20,30,40}
vlan_num.add(50)  # add() adds an item to set
print(vlan_num)
```

```console
{40, 10, 50, 20, 30}
```

To add multiple items all at once, then we should use the `update()` method.

```py
vlan_name = {10, 20, 30, 40}
vlan_name.update([50, 60])  # update() will take any iterable
print(vlan_name)
```

```console
{40, 10, 50, 20, 60, 30}
```

### Removing items

Removing items from sets have different ways.

You can use:

- discard()
- remove()
- pop()

The `discard()` method allows deleting elements without showing an error if there is no element in set

```py
vlan_num = {10, 20, 30, 40, 50}
vlan_num.discard(55)
print(vlan_num)
vlan_num.discard(50)
print(vlan_num)
```

```console
{50, 20, 40, 10, 30}
{20, 40, 10, 30}
```

The `remove()` method will remove the specified item from a set.

```py
vlan_num = {10, 20, 30, 40, 50}
vlan_num.remove(30)
print(vlan_num)
```

```console
{50, 20, 40, 10}
```
The `remove()` method will create an error if an item does not exist.

```py
vlan_num = {10, 20, 30, 40, 50}
print(vlan_num.remove(60))
```

```console
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 60
```
The `pop()` method will remove and return an item from the set.

```py
vlan_name = set(("tech", "guest", "accounts"))
print(vlan_name.pop())
```

```console
accounts
```

If a set is empty, trying to pop() an item, will create an error. Lists are ordered while sets are not, so you can’t be sure what you will be removing with `pop()` since sets are not ordered.

## Operations with sets

Sets are useful in performing different operations such as finding union of sets, intersection and so on. Union of sets can be obtained by `union` or operator `|`.

```py
vlan_num_one = {10, 20, 30, 50, 100}
vlan_num_two = {100, 101, 102, 102, 200}
print(vlan_num_one | vlan_num_two)  # combines two or more sets into a new set

print("-" * 35)

vlan_num = vlan_num_one.union(vlan_num_two)  # to save the new set, do the following
print(vlan_num)
```

```console
{100, 101, 102, 200, 10, 50, 20, 30}
-----------------------------------
{100, 101, 102, 200, 10, 50, 20, 30}
```

The `intersection()` method takes two sets and returns a new set that contains only the items that are the same in both sets. The intersection of sets can be obtained by `intersection` or operator `&`.

```py
vlan_num_one = {10, 20, 30, 50, 100}
vlan_num_two = {100, 101, 102, 102, 200}
vlan_num = vlan_num_one.intersection(vlan_num_two)  # intersection(), it returns a new set
print(vlan_num)

print("-" * 5)

print(vlan_num_one & vlan_num_two)  # same as intersection() 
```

```console
{100}
-----
{100}
```

The `difference()` method will return a new set with the elements in the set that are not in the other set.

```py
vlan_num_one = {10, 20, 30, 50, 100}
vlan_num_two = {100, 101, 102, 102, 200}
print(vlan_num_one.difference(vlan_num_two))

print("-" * 15)

print(vlan_num_two.difference(vlan_num_one))
```

```console
{50, 10, 20, 30}
---------------
{200, 101, 102}
```
