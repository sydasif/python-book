# Python Operator

Operators in Python are used to perform operations on variables and values.

Python divides the operators in the following groups:

- Arithmetic operators
- Assignment operators
- Comparison operators
- Logical operators
- Identity operators
- Membership operators

## Arithmetic Operators

Arithmetic operators are used with numeric values to perform common mathematical operations.

| Syntax      | Description | Example |
| ----------- | ----------- | ------- |
| +           | Addition    | 3 + 4   |
| -          | Subtraction | 1 - 5 |
| *          | Multiplication | 5 * 6 |
| /          | Division | 7 / 2 |
| %          | Modulus | 5 % 1 |
| **      | Exponentiation | 8 ** 3 |
| //      | Floor division | 3 // 8 |

```py
print(7 // 2) 
```

```console
3
```

```py
print(7 / 2)
```

```console
3.5
```

```py
print(5 % 3) # reminder
```

```console
2
```

## Assignment Operators

Assignment operators are used to assign values to variables.

| Syntax      | Example     | Same as |
| ----------- | ----------- | ------- |
| =           | x = 5    | x = 5  |
| +=          | x += 3    | x = x + 3 |
| -=          | x -= 3    | x = x - 3 |
| *=          | x *= 3    | x = x * 3 |
| /=          | x /= 3    | x = x / 3 |
| %=          | x %= 3    | x = x % 3 |
| //=         | x //= 3    | x = x // 3 |
| **=         | x **= 3    | x = x ** 3 |

```py
x = 3
print(x)
```

```console
3
```

```py
x += 3
print(x)
```

```console
6
```

## Comparison operators

Comparison operators are used to comparing two or more variables. There are seven main comparison operators in Python. These operators include:

| Syntax      | Description | Example |
| ----------- | ----------- | ------- |
| ==          | Equal       | x == y  |
| !=          | Not equal   | x != y  |
| >           | Greater than | x > y |
| <           | Less than | x < y |
| >=          | Greater than or equal to | x >= y |
| <=          | Less than or equal to | x <= y |

```py
a = 21
b = 10
c = 0

if ( a == b ):
    print ("Line 1 - a is equal to b")
else:
    print ("Line 1 - a is not equal to b")
```

```console
Line 1 - a is not equal to b
```

```py
a = 5
b = 20

if ( a <= b ):
    print ("Line 6 - a is either less than or equal to b")
else:
    print ("Line 6 - a is neither less than nor equal to b")
```

```console
Line 6 - a is either less than or equal to b
```

## Logical operators

Python has three main logical operators. These include:

- logical `and`
- logical `or` and logical `not`

To understand logical Operators how logical operators work, let’s evaluate logical expressions:

| Syntax      | Description | Example |
| ----------- | ----------- | ------- |
| and         | Returns True if both statements are true      | x < 5 and  x < 10 |
| or          | Returns True if one of the statements is true | x < 5 or x < 4 |
| not         | Reverse the result | not(x < 5 and x < 10) |

```py
x = 6
print(x < 5 and  x < 10)
```

```console
False
```

```py
x = 6
print(x < 5 or x > 4)
```

```console
True
```

## Identity Operators

Identity operators are used to compare the objects, not if they are equal, but if they are actually the same object, with the same memory location.

| Syntax      | Description | Example |
| ----------- | ----------- | ------- |
| is          | Returns True if both variables are the same object     | x is y     |
| is not      | Returns True if both variables are not the same object | x is not y |

## Membership Operators

Membership operators are used to test if a sequence is presented in an object.

| Syntax      | Description | Example |
| ----------- | ----------- | ------- |
| in          | Returns True if a sequence with the specified value is present in the object     | x in y     |
| not in      | Returns True if a sequence with the specified value is not present in the object | x not in y |
