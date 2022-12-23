# Numbers in Python

Python has only three built-in numeric types; these include integer, float and complex. These types are known by the value assigned to the variable.

## Integers

An integer is a whole number and not a fraction. You can create an integer in two ways in Python, the most common way is to assign an integer to a variable:

```py
num_one = 1
print(num_one)
```

```console
1
```

The other way to create an integer is to use the `int()` callable, like this:

```py
num_two = int(3)
print(num_two)
```

```console
3
```

You can do simple math with variables:

```py
1 + 2
1 - 2
```

```console
3
1
```

You won’t use `int()` to create an integer, usually `int()` is used for converting string or other types to an integer or called {ref}`Type Casting in Python`.

## Float

A float is refers to a number that has a decimal point in it. For example, `2.0` is a float while `2` is an integer. The most common way is to assign a float to a variable, and the other way to create a float is to use the `float()`.

```py
num_one = 1.5 
print(num_one)
```

```console
1.5
```

You can do simple math with variables:

```py
1.0 + 2.0
```

```console
3.0
```

```{Note}
Note that the arithmetic operation of the integer and floats will convert the result to float.
```

## Complex Number

A complex number has a real and an imaginary part, which is each a floating-point number. We can also use the `complex()` built-in function to create a complex number.

```py
z = 1j 
print(z)
```

```console
1j
```

## Boolean Values

In Python programming, you may need to know if an expression is `True` or `False`. You can evaluate any expression in Python, and get one of two answers. When comparing two values, the expression is evaluated and Python returns the Boolean value.

Booleans represent one of two values:

- True or
- False

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 10 < 12
True
```

The `bool()` built-in function creates a Boolean value and allows the program/code to evaluate any logic (expression), and give a Boolean value in return. This is because in Boolean logic all values are reduced to either `True` or `False`.

```{Note}
- Boolean valuse is a subclass of integer.
- It is case-sensitve, if you write `true` (instead of `True`), it will not work.
```

## None Type

The `None` keyword is used to define a null value or no value at all. `None` is not the same as `0`, `False`, or an empty string. `None` is a data type of its own (None Type) and only None can be None.

## Increment/Decrement a Number

Python numbers are immutable, we can use them in arithmetic and assign their value back with ease:

```py
x = 5
x = x + 1
```

```console
6
```

Here, we have defined a variable, `x`. In the next line, we take `x` and add `1` to it. Then, we store the result back into `x`, as a result `x` stores `6`.

Likewise, direct assignment also work just for decrement:

```py
x = 5
x = x - 1
```

```console
4
```

## Increment/Decrement with Assignment Operators

Like most programming languages, Python has a way to increment a number. That said, increment operator `+=`. 

```py
x = 5
x += 1
```

```console
6
```

Without introducing any additional syntax, we can decrement a number with ease:

```py
x = 10
x += -1
```

```console
9
```
