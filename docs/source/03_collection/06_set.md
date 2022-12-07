# Sets in Python

A set is a container of an unordered collection of 'unique' and immutable objects. A set is un-indexed, therefore, they do not support functions including slicing, indexing and any other function that is associated with sequencing.

Sets are used to store multiple items in a single variable.  Sets are a collection of data with no duplicates. They are very useful when it comes to removing duplicate data from data collections.

Python sets can have different items of different data types such as float, integer, string or even tuple. Python set elements cannot be changed but can only be added or updated

Elements/items in a set can, however, be removed from the set using the `discard()` or `remove()` functions from sets. The `discard()` function removes an item from the set and returns no error if such an item is not found. The `remove()` function, on the other hand, is used to remove an item from a list and raise an error if such an item is not found.

## Creating a Set

In Python, sets are written with curly brackets or using the built-in Python function `set()`.

```py
# Sets are written with curly brackets
fruit = {"apple", "banana", "cherry"}
print(fruit)
```

```console
{'apple', 'banana', 'cherry'}
```

When we `print()` the set, duplicates were removed automatically.

```py
# Sets cannot have two items with the same value
fruit = {"apple", "banana", "cherry", "apple"}
print(fruit)
```

```console
{'apple', 'banana', 'cherry'}
```

## The set() Constructor

It is also possible to use the `set()` constructor to make a set.

```py
fruit = set(("apple", "banana", "cherry"))
print(fruit)
```

```console
{'apple', 'banana', 'cherry'}
```

## Set methods

In set, we can’t change a value. However, we can add, remove etc.

### Adding Items

There are two ways to add items to a set:

- add()
- update()

```py
# add() adds an item to set
set1 = {10,20,30,40}
set1.add(50)
print(set1)
```

```console
{40, 10, 50, 20, 30}
```

To add multiple items all at once, then we should use the `update()` method.

```py
# update() will take any iterable
my_set = {10,20,30,40}
my_set.update(['d', 'e', 'f'])
print(my_set)
```

```console
{'d', 40, 10, 'f', 'e', 20, 30}
```

### Removing Items

Removing items from sets have several different ways.

You can use:

- discard()
- remove()
- pop()

```py
'''discard() allows deleting elements without showing 
an error if there is no element in set'''

set1 = {10, 20, 30, 40, 50}
set1.discard(55)
print(set1)
set1.discard(50)
print(set1)
```

```console
{50, 20, 40, 10, 30}
{20, 40, 10, 30}
```

The `remove()` method will remove the specified item from a set.

```py
# remove() will create an error if an item does not exist
set1 = {10, 20, 30, 40, 50}
set1.remove(30)
print(set1)
```

```console
{50, 20, 40, 10}
```

The `pop()` method will remove and return an item from the set.

```py
my_set = {"a", "b", "c"}
my_set.pop()
```

```console
'a'
```

If a set is empty, trying to pop() an item, will create an error. Lists are ordered while sets are not, so you can’t be sure what you
will be removing with `pop()` since sets are not ordered.

## Operations with sets

Sets are useful in performing different operations such as finding union of sets, intersection and so on.
Union of sets can be obtained by `union` or operator `|`.

```py
# combines two or more sets into a new set
set_num1 = {10,20,30,50,100}
set_num2 = {100,101,102,102,200}
print(set_num1 | set_num2)
print("-" * 35)
# to save the new set, then do the following
set_num3 = set_num1.union(set_num2)
print(set_num3)
```

```console
{100, 101, 102, 200, 10, 50, 20, 30}
-----------------------------------
{100, 101, 102, 200, 10, 50, 20, 30}
```

The `intersection()` method takes two sets and returns a new set that contains only the items that are the same in both sets. The intersection of sets can be obtained by `intersection` or operator `&`.

```py
# intersection(), it returns a new set
set_num1 = {10,20,30,50,100}
set_num2 = {100,101,102,102,200}
set_num3 = set_num1.intersection(set_num2)
print(set_num3)
print("-" * 5)
print(set_num1 & set_num2)
```

```console
{100}
-----
{100}
```

The `difference()` method will return a new set with the elements in the set that are not in the other set.

```py
set_num1 = {10,20,30,50,100}
set_num2 = {100,101,102,102,200}
print(set_num1.difference(set_num2))
print("-" * 15)
print(set_num2.difference(set_num1))
```

```console
{50, 10, 20, 30}
---------------
{200, 101, 102}
```
