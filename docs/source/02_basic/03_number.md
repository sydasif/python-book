# Python Numbers

Python has only three built-in numeric types; these include integer, float and complex. These types are known by the value assigned to the variable.

## Integers

You can create an integer in two ways in Python. The most common way is to assign an integer to a variable:

```py
# integer
num_int = 1
print(num_int)
```

```console
1
```

The other way to create an integer is to use the `int()` callable, like this:

```py
num_int = int(3)
print(num_int)
```

```console
3
```

You won’t use `int()` to create an integer, usually `int()` is used for converting string or other types to an integer or called type {ref}`Type Casting in Python`. `int()` takes an optional second argument for the base in which the first argument is to be interpreted. In other words, you can tell Python to convert to `base2`, `base8`, `base16` etc. The first argument has to be a string while the second argument is the base.

```py
int('101', 16)
```

```console
257
```

## Floats

A float in Python refers to a number that has a decimal point in it. For example, `2.0` is a float while `2` is an integer. The most common way is to assign a float to a variable, and the other way to create a float is to use the `float()`.

```py
# float
num_float = 1.5 
print(num_float)
```

```console
1.5
```

```py
num_float = float(10.5) 
print(num_float)
```

```console
10.5
```

## Complex Numbers

A complex number has a real and an imaginary part, which is each a floating-point number. We can also use the `complex()` built-in function to create a complex number.

```py
# complex
z = 1j 
print(z)
```

```console
1j
```

## Boolean Values

In Python programming, you may need to know if an expression is `True` or `False`. You can evaluate any expression in Python, and get one of two answers. When comparing two values, the expression is evaluated and Python returns the Boolean value.

Booleans represent two values:

- True or
- False

The `bool()` built-in function creates a Boolean value and allows the program/code to evaluate any logic (expression), and give a Boolean value in return. This is because in Boolean logic all values are reduced to either `True` or `False`.

```{Note}
`bool()` is a subclass of integer.
```

## None Type

The `None` keyword is used to define a null value or no value at all. `None` is not the same as `0`, `False`, or an empty string. `None` is a data type of its own (None Type) and only None can be None.
