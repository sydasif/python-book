# Dictionaries in Python

Dictionaries are used to store data/value in `key-value` pairs. A dictionary is a collection which is ordered, and mutable and does not allow duplicate keys, any key of the dictionary is associated (or mapped) to a value. Keys within a dictionary are 'unique' and must be from immutable data types such as strings or numbers.

```{Note}
As of Python version 3.7, dictionaries are ordered. In Python 3.6 and earlier, dictionaries are unordered.
```

## Creating Dictionaries

There are a couple of different ways, we can create a dictionary. The most common method is by placing a comma-separated list of `key: value` pairs within curly braces.

```py
credentials = {"user": "admin","pass": "p@wOrd", "secret": "cisco"}
print(credentials)
```

```console
{'user': 'admin', 'pass': 'p@wOrd', 'secret': 'cisco'}
```

Python’s built-in `dict()` function can create a dictionary. A `dict()` function accepts a series of keyword arguments `(1="one", 2="two")`, a list of tuples, or another dictionary.

```py
credentials_list = [
    ("user", "admin"),
    ("pass", "p@wOrd"),
    ("secret", "cisco"),
    ("iOS", 15.2)
]
credentials = dict(credentials_list)
print(credentials)
```

```console
{'user': 'admin', 'pass': 'p@wOrd', 'secret': 'cisco', 'iOS': 15.2}
```

Each `key` must be different in order to maintain uniqueness `i.e.` to get the correct information about a `value`.

### Accessing dictionaries

Dictionaries are very fast and can access any value in a dictionary via the key. If the key is not found, a `KeyError` will receive.

```py
credentials = {"user": "admin","pass": "p@wOrd", "secret": "cisco"}
print(credentials["pass"])
```

```console
p@wOrd
```

### Nested Dictionary

A dictionary within a dictionary is called a nested dictionary. It accumulated multiple dictionaries into one. Each dictionary will have its own key-value pair.

```py
device_list = {
    "cisco": {'r1': 'south', 's1': 'west'},
    'juniper': {'r2': 'east', 's2': 'north'}
    }
    
print(device_list['cisco'])
print(device_list['juniper']["s2"])
```

```console
{'r1': 'south', 's1': 'west'}
north
```

```{Note}
Dictionaries are lookup tables. They map from a `key` to a `value`.
```

## Modification of Dictionaries

Dictionary elements can be created, accessed, modified or deleted. While a dictionary is created, its elements will contain a `key-value` pair to be accessed. You can also delete some values or delete a complete dictionary using `del` and `clear` respectively.

To add a new item to a dictionary, use the square braces to enter a new key and set it to a value.

```py
credentials = {"user": "admin","pass": "p@wOrd", "secret": "cisco"}
credentials["iOS"] = 15.2
print(credentials)
```

```console
{'user': 'admin', 'pass': 'p@wOrd', 'secret': 'cisco', 'iOS': 15.2}
```

Setting a pre-existing key to a new value will overwrite the previous value.

```py
credentials = {"user": "admin","pass": "p@wOrd", "secret": "cisco"}
credentials["iOS"] = 12.2
print(credentials)
```

```console
{'user': 'admin', 'pass': 'p@wOrd', 'secret': 'cisco', 'iOS': 12.2}
```

The values in dictionary items can be of any data type.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
# Adding new key-value as a list
credentials["devices"] = ["cisco", "juniper", "arista"]
print(credentials)
```

```console
{'user': 'admin', 'pass': 'p@wOrd', 'devices': ['cisco', 'juniper', 'arista']}
```

Python’s `del` keyword removes the key-value.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
del credentials["user"]
print(credentials)
```

```console
{'pass': 'p@wOrd'}
```

The `clear()` method is used to remove all the items from the dictionary.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
credentials.clear()
print(credentials)
```

```console
{}
```

### Dictionary Method

As the most data types in Python, dictionaries have also special methods to use.

The `get()` method to get a value, if the key not found, default value `None` will return without any error.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
print(credentials.get("pass"))
```

```console
p@wOrd
```

If there is no key is present in dictionary `None` type will return.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
print(credentials.get("origin"))
```

```console
None
```

The `pop()` method removes the specified key from the dictionary and return the value of item.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
print(credentials.pop('user'))
```

```console
admin
```

The `keys()` method returns the keys of the dictionary, as a list.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
print(credentials.keys())  # print keys
```

```console
dict_keys(['user', 'pass'])
```

The `values()` method returns the values of the dictionary, as a list.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
print(credentials.values())  # print values
```

```console
dict_values(['admin', 'p@wOrd'])
```

The `items()` method returns the object contains the `key-value` pairs of the dictionary, as tuples in a list.

```py
credentials = {'user': 'admin', 'pass': 'p@wOrd'}
print(credentials.items())  # print key-value pair
```

```console
dict_items([('user', 'admin'), ('pass', 'p@wOrd')])
```
