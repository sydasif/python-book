# If-else Statement

`if` - `else` statement is a conditional statement in programming. If the statement is proved to be `True`, then a given set of code block (statement) are executed. If the statement is proved to be `False`, then another set of code block or none of the statement are executed.

- An `if` statement is written by using the `if` keyword.
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
You can use `if` without `else` statement also.
```

## Elif Statements

The `elif` keyword, if the previous conditions were not true, then try this condition. The general expression used to represent the nested `if` and multi-Way `if`, `elif` and `else` Statements is given below:

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

## Nested If-else Statement

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

## If-else and input() Function

In the code below we can mixed the `if` condition with `input()` function:

```py
user = input("Enter your Username: ")

if user == 'admin':
    password = input("Entef your Password: ")

    if password == 'cisco':
        print("Access granted...")
    else:
        print("Incorrect Password!!!")    

else:
    print("Incorrect Username!!!")
```

```console
Enter your Username: admin
Entef your Password: abc
Incorrect Password!!!
```

## If-else and Logical Operators

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

## Ternary Operator

Pyton ternary operator is commonly known as conditional expressions. These operators evaluate expressions based on a condition being true or false.

Here is an example of using these conditional expressions.

```py
num = True
a = f"num is {num}" if num else f"num is {num}"
print(a)
```

```console
num is True
```

````{Note} **code above is same as below**
```py
num = True
if num:
    a = f"num is {num}"
    print(a)
else:
    a = f"num is {num}"
    print(a)
```
````

Ternary Operator allows to quickly test a condition instead of a multiline if statement.
