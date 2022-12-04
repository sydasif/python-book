# Lists in Python

The list is the most versatile data type available in Python which can be written as a list of comma-separated values (items) between square brackets. Lists are created by separating values that are in square brackets. Lists are Python data structures which are mutable ordered sequences of elements. Each element in the list has a value called an item.

Lists are Python’s most flexible ordered collection (sequence) object type. Lists can contain any sort of object; numbers, strings and even other lists. Lists can contain another list called a `nested list`. The elements used in lists can be changed. This means lists can be mutated, unlike tuples or strings. They are mainly defined by having values inside brackets.

```py
# Example of a List 
week_day = ["Sunday", "Monday", "Friday"]
print(week_day)
```

```console
['Sunday', 'Monday', 'Friday']
```

Lists are used in Python where programmers need to work with many related values. They help in condensing the code by keeping the related data together hence allowing the programmer to perform the same functions and operations on multiple values at once. Each item in the list corresponds to a given index number. The index is an integer value starting from `0`. An example of a list is given below:

```py
a = [100, "bottles", ["on", "the", "earth"]]
print(a[2])
```

```console
['on', 'the', 'earth']
```

Lists can also be used for negative indexing.

```py
print(a[-1])
```

```console
['on', 'the', 'earth']
```

## Creation of List

The creation of lists is done by placing strings between brackets and separating them with commas. This is done by adding a name just before the brackets.

```py
# this is a list that is referenced using the name list_items

list_items = ['mango', 'juice', 'banana', 'tree', 'house', 'toy', 'cow', 'horse']
```

```{Note}
There are several ways to create a list:

- creates an empty list: `[]`
- Using the `list()` function: `list()`
```

To retrieve a list, there are two important elements are used. These elements are the name of the list and the position of the item in the list. It is important to note that the positioning of the items would start from a `zero`.

```py
print(list_items[0])
```

```console
mango
```

We can add, remove or sort for items in a list.

```py
fruit_list = ['apple', 'mango', 'carrot', 'banana']
print('I have', len(fruit_list), 'fruits to buy.')
```

```console
I have 4 fruits to buy.
```

```py
# Add an item to a list
fruit_list.append('rice')
print(fruit_list)
```

```console
['apple', 'mango', 'carrot', 'banana', 'rice']
```

```py
# sort a list
fruit_list.sort()
print(fruit_list)
```

```console
['apple', 'banana', 'carrot', 'mango', 'rice']
```

Elements in a list have the following characteristics:

- They are accessed via indices.
- They maintain their ordering unless explicitly re-ordered.
- They can be of any type, and types can be mixed.

## List Slicing

List slicing is a technique in python that helps read a list and return a specific segment of a list. The most important elements in list slicing are the full colons and negative signs. The name of the list is also an element that is used in the construction of a slicing statement. The example below shows how to list slicing is done in a single word.

```py
fruit_list = ['apple', 'mango', 'carrot', 'banana', 'rice']
print(len(fruit_list))
print(fruit_list[-1]) # 1st item from the end
print(fruit_list[-2]) # 2nd item from the end
print(fruit_list[1:3]) # index 3 not included
print(fruit_list[1:]) # until the end
```

```console
5
rice
banana
['mango', 'carrot']
['mango', 'carrot', 'banana', 'rice']
```

## List Function and Method

Lists have a few functions/method that are used to control and edit the data stored in a list.

- `.append()`

This method gives the chance to add an item/element to an existing list.

```py
fruit_name = ["mango", "banana", "orange", "apple"]
print(fruit_name)
fruit_name.append("grapes")
print(fruit_name)
```

```console
['mango', 'banana', 'orange', 'apple']
['mango', 'banana', 'orange', 'apple', 'grapes']
```

- `.insert()`

This function works the same as the function append but is more specific to the position at which the new item will appear in the existing list.

```py
fruit_name = ["mango", "banana", "orange", "apple"]
print(fruit_name)
fruit_name.insert(2, "grapes")
print(fruit_name)
```

```console
['mango', 'banana', 'orange', 'apple']
['mango', 'banana', 'grapes', 'orange', 'apple']
```

- `remove() & pop()`

This is used to delete an item from the list. Its syntax is the same as those of the other functions. When an item appears more than once in the list, the command `remove()` will only delete the item that appears the first in the list.

```py
fruit_name = ["mango", "orange", "banana", "orange", "apple"]
print(fruit_name)
fruit_name.remove("orange")
print(fruit_name)
```

```console
['mango', 'orange', 'banana', 'orange', 'apple']
['mango', 'banana', 'orange', 'apple']
```

If the command mentions an item that is not on the list, the functions will return an error which will indicate that the item is not on the list.

```py
fruit_name = ["mango", "orange", "banana", "orange", "apple"]
print(fruit_name)
```

```console
['mango', 'orange', 'banana', 'orange', 'apple']
```

```py
fruit_name.remove("tomato")
print(fruit_name)
```

```console
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
Cell In [16], line 3
      1 fruit_name = ["mango", "orange", "banana", "orange", "apple"]
      2 print(fruit_name)
----> 3 fruit_name.remove("tomato")
      4 print(fruit_name)

ValueError: list.remove(x): x not in list
```

To remove an item by position, the function `pop()` is used. When the method `pop()` is called without specifying the position, the last item is deleted. When this method is used, an item is deleted and the function returns the item that was deleted.

```py
fruit_name = ["mango", "orange", "banana", "orange", "apple"]
fruit_name.pop()  # last item will pop
```

```console
'apple'
```

```py
fruit_name = ["mango", "orange", "banana", "orange", "apple"]
fruit_name.pop(2)  # index 2 at number 3rd position will pop
```

```console
'banana'
```

- `extend()`

This method is used to add a list to another list. This method is different from append as it deals with joining of two lists. The method joins two lists by adding the second list to the end of the first list as shown in the example below.

```py
list1 = [1, 2, 3]
list1.extend([4, 5])
print(list1)
```

```console
[1, 2, 3, 4, 5]
```

To check attribute (method) of an object see {ref}`dir() method`.

```{seealso}
- [More on Lists](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists). Methods of list objects.
```

## [The `del` statement](https://docs.python.org/3/tutorial/datastructures.html#the-del-statement)

There is a way to remove an item from a list given its index instead of its value: the `del` statement. This differs from the `pop()` method which returns a value.

```py
# remove an item from list
del fruit_list[0]
print(fruit_list)
```

```console
['mango', 'carrot', 'banana', 'rice']
```
