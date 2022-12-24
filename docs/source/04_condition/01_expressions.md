# Boolean expressions

Boolean expressions are expressions in Python programming language that produces a boolean value when evaluated. The value can either be `True` or `False`. In Python, `False` maps to `0` (zero) and `True` maps to `1` (one). Boolean operations are used to control the flow of a program and make a comparison. Python also provides the `bool()` function, which allows you to cast other types to `True` or `False`.

This can be shown in the expressions below:

```py
num = bool(2)
if num == True:
    print(num)
```

```console
True
```

When you want to compare two values in Python, you need to use comparisons operator `==` instead of a single `=`. A single `=` is known as the assignment operator, as was mentioned in previous chapters. It assigns the value on the right to the variable on the left.

## What is False and True?

Almost any value is evaluated to `True` if it has:

- Any string is `True`, except empty strings.
- Any number is `True`, except `0`.
- Any `list`, `tuple`, `set`, and `dictionary` are `True`, except empty ones.

The following values are `False`:

- `0` (integer, float or complex)
- Empty collections: `“ ”`, `()`, `[]`, `{}`
- `None` type

## Comparisons Operator

In Python programming, the comparison operator is used to compare two values and evaluate them down to a single value that can either be `one` or `zero` or rather `True` or `False`. Boolean is a subclass of the `int` class. There are several boolean operators that can be used to evaluate an expression as either `True` or `False`.

These expressions include:

- Equals:                   `==`
- Not Equals:               `!=`
- Less than:                `<`
- Less than or equal to:    `<=`
- Greater than:             `>`
- Greater than or equal to: `>=`

```py
x = 5
y = 10

print(x == y)  # Is 5 equal to 10?
print(x != y)  # Is 5 not equal to 10?
```

```console
False
True
```

## Logical operator

Logical operators are operators that are used to compare two values and the final expression is evaluated down to a boolean value `True` or `False`. These logical operations are given in the table below:

- `and`
- `not`
- `or`

```py
print((10 > 5) and (2 < 4))
print((3 > 5) and (2 < 4))  
```

```console
True
False
```

For `AND` operator, both expressions must evaluate to `True` for the final boolean expression to be `True` else the final boolean value will be `False`.

```{epigraph} **Logic AND Truth Table**
| Expressions      | Result |
| ---------------- | -----  |
| True and True    | True   |
| True and False   | False  |
| False and True   | False  |
| False and False  | False  | 
```

For the `OR` operator, at least one of the two operators must evaluate to `True` for the final boolean expression to evaluate to `True`.

```py
print((10 > 5) or (2 < 4))
print((2 > 5) or (5 < 4)) 
```

```console
True
False
```

```{epigraph} **Logic OR Truth Table**
| Expressions     | Result |
| --------------- | -----  |
| True or True    | True   |
| True or False   | True   |
| False or True   | True   |
| False or False  | False  | 
```

`OR` operation can evaluate to `False` only, if both operations evaluate to `False`.

Lastly, `NOT` is the opposite of `False` and `True` which means, its inner expression is `True` for the new expression to evaluate to `False` else it will evaluate to `True`.

```{epigraph} **Logic NOT Truth Table**
| Expressions | Result |
| ----------- | ----- |
| not True    | False |
| not False   | True |
```

Expressions consist of values and operators, and they can always evaluate (that is, reduce) down to a single value.
