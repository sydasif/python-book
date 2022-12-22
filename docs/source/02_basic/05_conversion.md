# Type Casting in Python

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
# string
s = '132'

# typecast to integer
n = int(s)
print(n)
print(type(n))

# typecast to float
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

````{Note}
Please note that, if you have decimal point in the string, you cannot typecast that directly to an integer. You should first typecast string to float and then to an integer. Following is a quick code snippet for the same.

```py
# String
s = '132.564'
# Typecast to integer
n = int(float(s))
```
````
