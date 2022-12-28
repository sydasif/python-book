# Dictionaries in Python

Dictionaries are used to store data/value in `key-value` pairs. A dictionary is a collection which is ordered, and mutable and does not allow duplicate keys, any key of the dictionary is associated (or mapped) to a value. Keys within a dictionary are 'unique' and must be from immutable data types such as strings or numbers.

```{Note}
As of Python version 3.7, dictionaries are ordered. In Python 3.6 and earlier, dictionaries are unordered.
```

## Creating Dictionaries

There are a couple of different ways, we can create a dictionary. The most common method is by placing a comma-separated list of `key: value` pairs within curly braces.

```py
my_car = {"brand": "Ford","model": "Mustang", "year": 1992}
print(my_car)
```

```console
{'brand': 'Ford', 'model': 'Mustang', 'year': 1992}
```

Python’s built-in `dict()` function can create a dictionary. A `dict()` function accepts a series of keyword arguments `(1="one", 2="two")`, a list of tuples, or another dictionary.

```py
numbers = dict(one=1, two=2, three=3)
print(numbers)
```

```console
{'one': 1, 'two': 2, 'three': 3}
```

```py
info_list = [('first_name', 'Ali'), ('last_name', 'Ahmed')]
info_list = dict(info_list)
print(info_list)
```

```console
{'first_name': 'Ali', 'last_name': 'Ahmed'}
```

Each `key` must be different in order to maintain uniqueness `i.e.` to get the correct information about a `value`.

### Accessing dctionaries

Dictionaries are very fast and can access any value in a dictionary via the key. If the key is not found, a `KeyError` will receive.

```py
my_car = {"brand": "Ford", "model": "Mustang", "year": 1992}
print(my_car["brand"])
```

```console
Ford
```

### Nested Dictionary

A dictionary within a dictionary is called a nested dictionary. It accumulated multiple dictionaries into one. Each dictionary will have its own key-value pair.

```py
my_family = {
    "parents": {'dad': 'mike', 'mom': 'carol'},
    'kids': {'youngest': 'Ali', 'middle': 'jan', 'oldest': 'saira'}
    }
    
print(my_family['parents'])
print(my_family['kids'])
print(my_family['parents']["mom"])
print(my_family['kids']["middle"])
```

```console
{'dad': 'mike', 'mom': 'carol'}
{'youngest': 'Ali', 'middle': 'jan', 'oldest': 'saira'}
carol
jan
```

```{Note}
Dictionaries are lookup tables. They map from a `key` to a `value`.
```

## Modification of Dictionaries

Dictionary elements can be created, accessed, modified or deleted. While a dictionary is created, its elements will contain a `key-value` pair to be accessed. You can also delete some values or delete a complete dictionary using `del` and `clear` respectively.

To add a new item to a dictionary, use the square braces to enter a new key and set it to a value.

```py
my_car = {"brand": "Ford","model": "Mustang", "year": 1992}
my_car["year"] = 2000
print(my_car)
```

```console
{'brand': 'Ford', 'model': 'Mustang', 'year': 2000}
```

Setting a pre-existing key to a new value will overwrite the previous value.

```py
my_car = {"brand": "Ford","model": "Mustang", "year": 1992}
my_car["year"] = 2020
print(my_car)
```

```console
{'brand': 'Ford', 'model': 'Mustang', 'year': 2020}
```

The values in dictionary items can be of any data type.

```py
my_car["colors"] = ["black", "red", "blue"] # Adding new key-value as a list
print(my_car)
```

```console
{'brand': 'Ford', 'model': 'Mustang', 'colors': ['black', 'red', 'blue']}
```

Python’s `del` keyword removes the key-value.

```py
del my_car["year"]
print(my_car)
```

```console
{'brand': 'Ford', 'model': 'Mustang'}
```

The `clear()` method is used to remove all the items from the dictionary.

```py
my_car = {"brand": "Ford","model": "Mustang","year": 1992}
my_car.clear()
my_car
```

```console
{}
```

### Dictionary Method

As the most data types in Python, dictionaries have also special methods to use.

The `get()` method to get a value, if the key not found, default value `None` will return without any error.

```py
my_car = {"brand": "Ford","model": "Mustang","year": 1992}
my_car.get("model")
```

```console
'Mustang'
```

```py
my_car = {"brand": "Ford","model": "Mustang","year": 1992}
print(my_car.get("origin"))
```

```console
None
```

The `pop()` method removes the specified key from the dictionary and return the value of item.

```py
my_car = {"brand": "Ford","model": "Mustang", "year": 1992}
my_car.pop('year')
```

```console
1992
```

The `keys()` method returns the keys of the dictionary, as a list.

```py
my_car = {"brand": "Ford","model": "Mustang","year": 1992}
print(my_car.keys())  # print keys
```

```console
dict_keys(['brand', 'model', 'year'])
```

The `values()` method returns the values of the dictionary, as a list.

```py
my_car = {"brand": "Ford","model": "Mustang","year": 1992}
print(my_car.values())  # print values
```

```console
dict_values(['Ford', 'Mustang', 1992])
```

The `items()` method returns the object contains the `key-value` pairs of the dictionary, as tuples in a list.

```py
my_car = {"brand": "Ford","model": "Mustang","year": 1992}
print(my_car.items())  # print key-value pair
```

```console
dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1992)])
```
