# If - Statement

`if` - `else` statement is a conditional statement in programming. If the statement is proved to be `True`, then a given 
set of code block (statement) are executed. If the statement is proved to be `False`, then another set of code block or 
none of the statement are executed.

An `if` statement is written by using the `if` keyword.

```py
is_up = "up"
if is_up == "up":
    print("interface is up")
```

```console
interface is up
```

The `else` keyword catches anything which isn't caught by the preceding conditions.

```py
is_up = "down"
if is_up == "up":
    print("interface is up")
else:
    print("interface is down")
```

```console
interface is down
```

## Elif Statements

The `elif` keyword, if the previous conditions were not true, then try this condition. The general expression used to 
represent the nested `if` and multi-Way `if`, `elif` and `else` Statements is given below:

```py
is_up = "shut"
if is_up == "up":
    print("interface is up")
elif is_up == "shut":
    print("interface is shut by admin")
else:
    print("interface is down")
```

```console
interface is shut down by admin
```

In the code below we can mixed the `if` condition with `input()` function:

```py
user = input("Enter your username: ")

if user == "ali":
    print("You are authorized to proceed...")
elif user == "bob":
    print("You are authorized to proceed...")
else:
    print("You are not authorized to proceed...")
```

```console
Enter your username: bob
You are authorized to proceed...
```

## If- else and Logical Operators

In case of `AND`, if both the operands are `True` then condition becomes `True`. If any of the operators is `False` 
then the condition evaluations to `False`.

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

For the `OR` operator, if any of the two operands are `True` then condition becomes `True`. If both operators are 
`False` then the condition becomes `False`.

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

## Ternary Operator

Pyton ternary operator is commonly known as conditional expressions. These operators evaluate expressions based on a 
condition being true or false.

Here is an example of using these conditional expressions.

```py
num = True
print(Numbers is true) if num else print(Number is false)
```

```console
num is True
```

````{Note} **code above is same as below**
```py
num = True
if num:
    print(Number is true)
else:
    print(Numbers is false)
```
````

Ternary Operator allows to quickly test a condition instead of a multiline if statement.
