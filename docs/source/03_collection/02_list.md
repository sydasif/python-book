# List in Python

The list in Python is the most multipurpose data type available in Python which can be written as a list of comma-separated values (items) between square brackets. Lists are Python data structures which are mutable and ordered. Each element in the list has a value called an item.

Lists are Python’s most flexible ordered collection (sequence) object type. Lists can contain any sort of object; numbers, strings and even another list called a `nested list`. The elements used in lists can be changed, which means lists can be mutated, unlike tuples or strings.

```py
vlans = ["vlan10", "vlan20", "vlan30"]
print(vlans)
```

```console
["vlan10", "vlan20", "vlan30"]
```

To reassign an item in list as below:

```py
vlans = ["vlan10", "vlan20", "vlan30"]
vlans[2] = "vlan5"
print(vlans)
```

```console
['vlan10', 'vlan20', 'vlan5']
```

Lists are used in Python where programmers need to work with many related values. They help in reducing the code by keeping the related data together, allowing it to perform the same functions and operations on multiple values at once. An example of a list is given below:

```py
my_list = [100, "bottles", ["on", "the", "earth"]]
print(my_list[2])
```

```console
['on', 'the', 'earth']
```

The creation of lists is done by placing values between brackets and separating them with commas. This is done by adding a name just before the brackets.

```py
list_of_ip = ['192.168.1.1', '192.168.1.2', '192.168.1.3']
```

```{Note} There are several ways to create a list:
- creates an empty list: `[]`
- Using the `list()` function: `list()`
```

Each item in the list links to a given index number. The index is an integer value starting from `0`. To retrieve a list, there are two important elements are used. These are the name of the list and the position of the item in the list.

```py
print(list_of_items[0])
```

```console
192.168.1.1
```

It is important to note that the positioning of the items would start from a `0`.

## Negative Indexes

While indexes start at `0`, you can also use negative number for the index. The value `-1` refers to the last index in a list, the value `-2` refers to the second-to-last index in a list, and so on.

Elements in a list have the following characteristics:

- They are accessed via indices.
- They maintain their ordering unless explicitly re-ordered.
- They can be of any type, and types can be mixed.

## List Concatenation

The `+` operator can be used to concatenate two lists. It appends one list at the end of the other list and results in a new list as output.

```py
list1 = [10, 11, 12, 13, 14] 
list2 = [20, 30, 42] 

result = list1 + list2
print(result) 
```

```console
[10, 11, 12, 13, 14, 20, 30, 42]
```

## List Method

Lists have a few functions/methods that are used to control and manage the data stored in a list.

### append() method

This method gives the chance to add an item/element to an existing list.

```py
vlan_name = ["mgmt", "prod", "tech", "acct"]
print(vlan_name)
vlan_name.append("guest")
print(vlan_name)
```

```console
["mgmt", "prod", "tech", "acct"]
["mgmt", "prod", "tech", "acct", "guest"]
```

### insert() method

This function works the same as the function `append()` but is more specific to the position at which the new item will appear in the existing list.

```py
vlan_name = ["mgmt", "prod", "tech", "acct"]
print(vlan_name)
vlan_name.insert(2, "guest")
print(vlan_name)
```

```console
["mgmt", "prod", "tech", "acct"]
["mgmt", "prod", "guest", "tech", "acct"]
```

### remove() and pop() method

This is used to delete an item from the list. Its syntax is the same as those of the other functions. When an item seems more than once in the list, the command `remove()` will only delete the item that appears first in the list.

```py
vlan_name = ["mgmt", "prod", "guest", "tech", "acct"]
print(vlan_name)
vlan_name.remove("guest")
print(vlan_name)
```

```console
["mgmt", "prod", "guest", "tech", "acct"]
["mgmt", "prod", "tech", "acct"]
```

If the command mentions an item that is not on the list, the functions will return an error which will indicate that the item is not on the list.

```py
vlan_name = ["mgmt", "prod", "guest", "tech", "acct"]
vlan_name.remove("tomato")
print(vlan_name)
```

```console
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
Cell In [16], line 3
      1 vlan_name = ["mgmt", "prod", "guest", "tech", "acct"]
----> 2 vlan_name.remove("tomato")
      3 print(vlan_name)

ValueError: list.remove(x): x not in list
```

To remove an item by position, the function `pop()` is used. When the method `pop()` is called without stating the position, the last item is deleted. When this method is used, an item is deleted and the function returns the item that was deleted.

```py
vlan_name = ["mgmt", "prod", "guest", "tech", "acct"]
vlan_name.pop()  # last item will pop
```

```console
'acct'
```

```py
vlan_name = ["mgmt", "prod", "guest", "tech", "acct"]
vlan_name.pop(2)  # index 2 at number 3rd position will pop
```

```console
'guest'
```

### extend() method

This method is used to add a list to another list. This method is different from append as it deals with the joining of two lists. This method joins two lists by adding the second list to the end and modified the first list as shown in the example below.

```py
list1 = [1, 2, 3]
list1.extend([4, 5])
print(list1)
```

```console
[1, 2, 3, 4, 5]
```

We can also sort items in a list.

```py
vlan_name = ["mgmt", "prod", "guest", "tech", "acct"]
```

```py
vlan_name.sort()
print(vlan_name)
```

```console
['acct', 'guest', 'mgmt', 'prod', 'tech']
```

To check the attribute (method) of an object see {ref}`dir() Function`.

## [The del statement](https://docs.python.org/3/tutorial/datastructures.html#the-del-statement)

There is a way to remove an item from a list given its index instead of its value: the `del` statement. This differs from the `pop()` method which returns a value.

```py
# remove an item from the list
del vlan_name[0]
print(vlan_name)
```

```console
['guest', 'mgmt', 'prod', 'tech']
```

## List Slicing

List slicing is a technique in Python that helps read a list and returns a specific segment of a list in the form of a new list. The most important thing in list slicing is the colon `:` and name of the list that is used in the creation of a slicing statement. The example below shows how to list slicing is done in a single word.

```py
vlan_name = ["mgmt", "prod", "guest", "tech", "acct"]
print(vlan_name[:4])
print(vlan_name[1:3])  # index 3 not included
print(vlan_name[0:])
```

```console
['mgmt', 'prod', 'guest', 'tech']
['prod', 'guest']
['mgmt', 'prod', 'guest', 'tech', 'acct']
```

As a shortcut, leaving out the first index is the same as using 0, or the beginning of the list. Leaving out the second index is the same as using the length of the list, which will slice to the end of the list.

```{seealso}
- [More on Lists](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists). Methods of list objects.
```
