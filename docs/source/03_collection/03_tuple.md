# Tuple in Python

A tuple is a list of items enclosed in parentheses, is to be immutable (can't be changed) and more efficient. A tuple is
a data structure that helps in the organization of data in Python. Since lists do the same purpose as a tuple, it can be
hard to differentiate between the two. The main difference, however, is that once tuples have been created, they are 
hard to change/modified. The main difference between tuples and lists is that tuples are immutable while lists aren’t.

```py
router_01 = ('hostname', 'location', 'vendor', 'model', 'ios', 'ip')
```

## Creating Tuples

You can create tuples in different ways, as above one of the simplest methods to create a tuple is to have a sequence of
values separated by commas. Those values could be integers, lists, dictionaries, or any other object, however; parentheses 
by themselves do not make a tuple:

```py
num_tup = (3)  # this is an integer
print(type(num_tup))
```

```console
<class 'int'>
```

Only using a comma might be confusing, always use parentheses to make it explicit.

```py
a_tuple = 4,  # this is tuple
print(type(a_tuple))
a_tuple = (4,)  # note the trailing comma
print(type(a_tuple))
```

```console
<class 'tuple'>
<class 'tuple'>
```

```{Note}
You can also create a tuple using the `tuple()` function.
```

## Tuple Method

There are not many ways to work with tuples because they are immutable. If you were to run `dir(tuple())`, you would 
find that tuples have only two methods:

- count()
- index()

You can use `count()` to find out how many elements match the value that you pass in.

```py
num_tup = (1, 2, 3, 4, 4,)
print(num_tup.count(4))
```

```console
2
```

Indexing in a tuple is used to find a specific element, as previously discussed in lists, tuple indexing also starts
with `0`. This means that the first item's position is `0` and the second is `1`.

```py
router_01 = ('hostname', 'location', 'vendor', 'model', 'ios', 'ip')
print(router_01[0])  # print at index 0
```

```console
hostname
```

If we modify an element in a tuple, this causes a `TypeError` to be raised because tuples are immutable and cannot be changed.

```py
router_01 = ('hostname', 'location', 'vendor', 'model', 'ios', 'ip')
router_01[0] = "horse"
```

```console
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
Cell In [15], line 1
----> 1 router_01[0] = "horse"

TypeError: 'tuple' object does not support item assignment
```

## Concatenating Tuples

Tuples can be joined together; in programming, this is called “concatenation”, however; concatenation will end up creating a new tuple.

```py
mgmt_ip = ('172.16.10.100',)
router_01 = ('hostname', 'location', 'vendor', 'model', 'ios')
print(mgmt_ip + router_01)
```

```console
('172.16.10.100', 'hostname', 'location', 'vendor', 'model', 'ios')
```

## Slicing in Tuples

The slicing function is used to get a part of the tuple. The main elements used in tuple slicing are the index and the 
slicing operator `:` the example below explains how slicing is done with tuples.

```py
router_01 = ('ip', 'hostname', 'location', 'vendor', 'model', 'ios')
print(router_01[2:])  # print index 2 and onward
```

```console
('location', 'vendor', 'model', 'ios')
```

```py
router_01 = ('ip', 'hostname', 'location', 'vendor', 'model', 'ios')
print(router_01[:2])  # print before index 2
```

```console
('ip', 'hostname')
```

## Tuples and Lists Differences

The difference between a list and a tuple is that lists are mutable while tuples are immutable. Due to this tuples are 
simpler, they never change and don’t have any of the useful properties found in lists that make working with lists so powerful.
