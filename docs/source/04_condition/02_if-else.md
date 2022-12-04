# If-else statement

If-else statement is a conditional statement in programming. If the statement is proved to be `True`, then a given set of programming statements are executed. If the statement is proved to be `False`, then another set of programming statements or none of the programming statements are executed.

- An 'if statement' is written by using the `if` keyword.
- The `elif` keyword in Python, "if the previous conditions were not true, then try this condition".
- The `else` keyword catches anything which isn't caught by the preceding conditions.

```py
x = 1
y = 0
if x > 0:
    print(x)
else:
    print(y)
```

```console
1
```

```{Note}
We can use `if` without `else` statement also.
```

## if elif and else Statements

The general expression used to represent the nested `if` and Multi-Way `if-elif-else` Statements is given below:

```py
num = 0
if num > 0:
    print("Number is greater then zero")
elif num == 0:
    print("Number is Zero")
else:
    print("Number is less then zero")        
```

```console
Number is Zero
```

## Nested if-else statement

We can use nested statement as below:

```py
num = 0
if num >= 0:
    if num == 0:
        print("Zero")
    else:
        print("+ve Number")
else:
    print("-ve Number")        
```

```console
Zero
```

## if-else and logical operators

In case of `AND`, if both the operands are `True` then condition becomes `True`. If any of the operators is `False` then the condition evaluations to `False`.

```py
num = 9
if num > 0 and num < 10:
    print(num)
```

```console
9
```

```py
num = 0
if num > 0 and num < 10:
    print(num)
else:
    print("Number is out of range")    
```

```console
Number is out of range
```

For the `OR` operator, if any of the two operands are `True` then condition becomes `True`. If both operators are `False` then the condition becomes `False`.

```py
a = 200
b = 33
c = 500

if a > b or a > c:
  print("At least one of the conditions is True")
```

```console
At least one of the conditions is True
```

For the `NOT` operator, on the other hand, if a condition evaluates to `True` then it becomes `False` and vice versa.
