# Python Variables

A variable is a storage location with a name and a value in Python, variables are names that can be assigned to a value and then used to refer to that value in your code. Variables are fundamental to programming for two reasons:

- Variables keep values accessible
- Variables give values perception
- Variables make change easy

## Creating Variables

Python has no command for declaring a variable. A variable is created at the moment you first assign a value to it.

```py
hostname = "localhost"
print(hostname)
```

```console
localhost
```

```py
ip_addr = "10.1.1.1"
print(ip_addr)
```

```console
10.1.1.1
```

You can get the data type of a variable with the `type()` function.

```py
ip_addr = "10.1.1.1"
print(ip_addr)
```

```console
<class 'str'>
```

## Assignment Statements

An operator is a symbol that operates on one or more values. Values are assigned to a variable using a special symbol called the assignment operator `=`. The `=` operator takes the value to the right of the operator and assigns it to the name on the left.

```py
hostName = "Router-01"
print(hostName)
```

```console
Router-01
```

String variables can be declared either by using single `' '` or double quotes `" "`.

```py
hostName = "Router-01"
print(hostName)
```

```console
Router-01
```

```py
hostName = 'Router-01'
print(hostName)
```

```console
Router-01
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

## The print() Function

The `print()` function displays the string/variable inside the parentheses on the screen. The line `print('Hello world!')` means “Print out the text in the string 'Hello world!'.”  A value that is passed to a function call is an argument.

```py
print("Hello, World!")
```

```console
Hello, World!
```

## Type Casting in Python

Type casting is a method used to change the variable value into a different data type to match the operation required to be performed by the programmer. In python, this feature can be accomplished by using built-in functions like `int()`, `str()`, `float()`, etc.

In this example, you will take an integer literal assigned to a variable. Then typecast this integer to float using the `float()` function.

```py
# integer
num = 100
# float
num_float = float(num)
print(num_float)
print(type(num_float))
```

```console
100.0
<class 'float'>
```

In the following code, you set a variable with a float value. Then typecast this float to an integer using `int()`.

```py
# float
num = 99.9
# integer
num_int = int(num)
print(num_int)
print(type(num_int))
```

```console
99
<class 'int'>
```

In this example, you will use `int()` and `float()` to typecast a string literal to integer and float.

```py
#string
s = '132'

#typecast to integer
n = int(s)
print(n)
print(type(n))

#typecast to float
f = float(s)
print(f)
print(type(f))
```

```console
132
<class 'int'>
132.0
<class 'float'>
```

````{margin}
Please note that, if you have decimal point in the string, you cannot typecast that directly to an integer. You should first typecast string to float and then to an integer. Following is a quick code snippet for the same.

```py
# String
s = '132.564'
# Typecast to integer
n = int(float(s))
```
````
