# Collections and Sequences in Python

In Python, collections and sequences are essential tools for grouping multiple values together. They help you manage and organize data efficiently, whether it's a list of numbers or a dictionary of key-value pairs.

Collections are like containers that hold multiple items. They come in different types, allowing you to store objects with or without a specific order. You can add, remove, and iterate over items in a collection. Common types of collections include:

- **Dictionaries**: Store key-value pairs and maintain the order of insertion.
- **Sets**: Store unique elements without any specific order.

Sequences are a type of collection that maintains a specific order of items. The order in which you add items is the order in which you retrieve them. Common sequence types include:

- **Strings**: Immutable sequences of characters.
- **Lists**: Mutable sequences that can store a collection of items.
- **Tuples**: Immutable sequences that can store a collection of items.

## Key Differences

- **Order**: Sequences maintain a specific order, while collections like sets do not.
- **Indexing**: You can access items in sequences by their position using an index. Collections like sets and dictionaries do not support indexing.
- **Mutability**: Lists are mutable (you can change them), while tuples and strings are immutable (you cannot change them). Sets and dictionaries are mutable.

Understanding these concepts will help you effectively manage and manipulate data in your Python programs. Whether you need to store items in a specific order or just group unique elements together, Python's collections and sequences provide the tools you need.

```{toctree}
:maxdepth: 2

01_list
02_tuple
03_set
04_dict
05_mutable
06_list_comp
07_set_comp
```
