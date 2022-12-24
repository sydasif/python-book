# Type Casting in Python

Type casting is a method used to change the variable value into a different data type to match the operation required to be performed by the programmer. In python, this feature can be accomplished by using built-in functions like `int()`, `str()`, `float()`, etc.

In this example, you will take an integer literal assigned to a variable. Then typecast this integer to float using the `float()` function.

```py
num = 100  # integer
num = float(num)  # typecast in float
print(num)
print(type(num))
```

```console
100.0
<class 'float'>
```

In the following code, you set a variable with a float value. Then typecast this float to an integer using `int()`.

```py
num = 99.9  # float
num = int(num)  # typecast in integer
print(num)
print(type(num))
```

```console
99
<class 'int'>
```

In this example, you will use `int()` and `float()` to typecast a string literal to integer and float.

```py
s = '132'  # string

n = int(s)  # typecast to integer
print(n)
print(type(n))

f = float(s)  # typecast to float
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
s = '132.564'  # String
n = int(float(s))  # typecast to integer
```
````
