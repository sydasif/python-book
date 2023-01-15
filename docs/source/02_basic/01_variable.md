# Variable in Python

Python variable is a storage container or to reserve a memory location with a name to store a value or data temporally and then used to refer to that value in your code. Variables are fundamental to any programming language.

- Variables keep values accessible
- Variables give values perception
- Variables make change easy
- Variables have data types

## Variable Declaration

Python is a dynamically typed language, a variable is created when you first assign a value to it. Variables do not need to be declared with any particular type, and can even be changed after they have been set.

```py
name = "Ali"
print(name)
```

```console
Ali
```

You can get the data type of a variable with the `type()` function.

```py
addr = "Pakistan"
print(addr)
```

```console
<class 'str'>
```

Assign values to multiple variables in one statement.

```py
age, city = 23, "Karachi"
print(age, city)
```

```console
23 Karachi
```

Assign the same value to multiple variables at once.

```py
age = num = 40
print(age, num)
```

```console
40 40
```

If you have a collection of values in a list, tuple etc. Python allows you to extract the values into variables.

```py
ip_addr_list = ["10.10.10.10", "172.16.10.10", "192.168.10.10"]

ip_addr1, ip_addr2, ip_addr3 = ip_addr_list

print(ip_addr1)
print(ip_addr2)
print(ip_addr3)
```

```console
10.10.10.10
172.16.10.10
192.168.10.10
```

### Assignment statements

An operator is a symbol that operates on one or more values. Values are assigned to a variable using a special symbol called the assignment operator `=`. The `=` operator takes the value to the right of the operator and assigns it to the name on the left.

```py
hostName = "R-01"
print(hostName)
```

```console
R-01
```

String variables can be declared either by using single `'R-01'` or double quotes `"R-01"`.

```py
hostName = "R-01"
print(hostName)
```

```console
R-01
```

```py
hostName = 'R-01'
print(hostName)
```

```console
R-01
```

## Variable Naming Convention

Variable names can be as long or as short as you like, but there are a few rules to follow.

- A variable name must start with a letter or the underscore character.
- A variable name cannot start with a number.
- A variable name can only contain alpha-numeric characters and underscores (`A-z`, `0-9`, and `_` ).
- `keywords` are reserved words that cannot be used as variable names or other identifiers.
- Variable names are case-sensitive.

```py
# Camel Case - Each word, except the first, starts with a capital letter:
myVariableName = "Ali"
# Pascal Case - Each word starts with a capital letter:
MyVariableName = "Ali"
# Snake Case - An underscore character separates each word:
my_variable_name = "Ali"
```

```{Note}
Use a more descriptive name such as `vlan_name` or `number_of_route`.
```
