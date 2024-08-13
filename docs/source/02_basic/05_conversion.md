## Type Casting and Useful Built-in Functions in Python

### Type Casting

Type casting is a method used to change the data type of a variable to match the operation you want to perform. In Python, you can use built-in functions like `int()`, `str()`, `float()`, etc., to achieve this.

#### Example 1: Integer to Float

Convert an integer to a float using the `float()` function.

```python
num = 100  # integer
num = float(num)  # convert to float
print(num)
print(type(num))
```

Output:

```console
100.0
<class 'float'>
```

#### Example 2: Float to Integer

Convert a float to an integer using the `int()` function.

```python
num = 99.9  # float
num = int(num)  # convert to integer
print(num)
print(type(num))
```

Output:

```console
99
<class 'int'>
```

#### Example 3: String to Integer and Float

Convert a string literal to an integer and a float using `int()` and `float()`.

```python
s = '132'  # string

n = int(s)  # convert to integer
print(n)
print(type(n))

f = float(s)  # convert to float
print(f)
print(type(f))
```

Output:

```console
132
<class 'int'>
132.0
<class 'float'>
```

#### Note on Converting Strings with Decimals

If your string contains a decimal point, you can't directly convert it to an integer. First, convert the string to a float and then to an integer.

```python
s = '132.564'  # string
n = int(float(s))  # convert to integer
print(n)
print(type(n))
```

### Useful Built-in Functions

Python comes with several built-in functions that you can use right away. Here are some of the most useful ones:

#### `len()` Function

The `len()` function returns the number of characters in a string.

```python
print(len('hello'))
```

Output:

```console
5
```

#### `bin()` Function

The `bin()` function converts an integer to its binary representation.

```python
num = 100
print(bin(num))  # print binary number
```

Output:

```console
0b1100100
```

Note: The prefix `0b` indicates that the result is a binary string.

#### `oct()` Function

The `oct()` function converts an integer to its octal representation.

```python
num = 100
print(oct(num))  # print octal number
```

Output:

```console
0o144
```

#### `hex()` Function

The `hex()` function converts an integer to its hexadecimal representation.

```python
num = 100
print(hex(num))  # print hex number
```

Output:

```console
0x64
```

Note: The prefix `0x` indicates that the result is a hexadecimal string.

#### `round()` Function

The `round()` function returns a floating-point number rounded to a specified number of decimal places.

```python
num = round(5.12345, 2)
print(num)
```

Output:

```console
5.12
```

#### `id()` Function

The `id()` function returns a unique identifier for an object, which is its memory address.

```python
num = 5.12
print(id(num))
```

Output:

```console
1707832475504
```

Note: The id is the object's memory address and will be different each time you run the program, except for some objects like integers from `-5` to `256`.
