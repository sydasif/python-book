# Variables in Python

A variable is a storage/reserve memory location with a name and a value in Python, variables are names that can be assigned to a value and then used to refer to that value in your code. Variables are fundamental to programming:

- Variables keep values accessible
- Variables give values perception
- Variables make change easy
- Variables have data types

## Variable Declaration

Python has no command for declaring a variable. A variable is created at the moment you first assign a value to it.

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

### Assignment Statements

An operator is a symbol that operates on one or more values. Values are assigned to a variable using a special symbol called the assignment operator `=`. The `=` operator takes the value to the right of the operator and assigns it to the name on the left.

```py
hostName = "R-01"
print(hostName)
```

```console
R-01
```

String variables can be declared either by using single `' '` or double quotes `" "`.

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
- `keywords` that are reserved words that cannot be used as variable names or any other identifiers.
- Variable names are case-sensitive (`myVariableName`, `MyVariableName` and `my_variable_name` are three different variables).

```py
# Camel Case - Each word, except the first, starts with a capital letter:
myVariableName = "Ali"
# Pascal Case - Each word starts with a capital letter:
MyVariableName = "Ali"
# Snake Case - Each word is separated by an underscore character:
my_variable_name = "Ali"
```

```{Note}
Use a more descriptive name such as `age`, `car_name`, or `total_volume`.
```
