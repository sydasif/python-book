## Conditional Statements in Python

Conditional statements in Python help control the flow of your program. They let you run specific blocks of code based on whether certain conditions are true or false.

An **expression** is a piece of code that can be evaluated to produce a value. Expressions usually involve variables, constants, and operators. Conditions, which determine which code blocks to execute, are made using these expressions.

Here are the main types of conditional statements in Python:

- **if statement**: This runs a block of code if a condition is true.
- **elif statement**: This checks multiple conditions one after another. If one condition is true, it runs the corresponding block of code.
- **else statement**: This runs a block of code if none of the previous conditions are true.

These statements make your Python programs flexible and able to handle different scenarios based on whether conditions are true or false.

## Importance of Conditions in Programming

Conditions are essential in programming because they make your code dynamic and responsive. They allow you to make decisions based on various factors and guide your program along different paths.

Here's an example:

```python
ip_addr = "10.1.1.1."
if "10" in ip_addr:
    print("Address Found")
```

In this example, the variable `ip_addr` holds an IP address as a string. The `if` statement checks if the string "10" is in `ip_addr`. If it is, the code inside the `if` block runs, printing "Address Found." The condition `"10" in ip_addr` is true if "10" is found in `ip_addr`, and false otherwise.

## Conditional Statements - `elif` and `else`

The `elif` statement is used to check another condition if the previous `if` condition is `False`. If the `if` condition is `True`, the code inside the `if` block runs. If it's `False`, Python checks the condition in the `elif` statement.

Here's an example:

```python
ssh_timeout = 20
if ssh_timeout == 10:
    print("SSH TimeOut: 10 sec")
elif ssh_timeout > 30:
    print("SSH TimeOut Greater Than: 30 sec")
else:
    print("Unexpected SSH TimeOut")
```

In this example:

- If `ssh_timeout` is `10`, it prints "SSH TimeOut: 10 sec."
- If `ssh_timeout` is more than `30`, it prints "SSH TimeOut Greater Than: 30 sec."
- If neither condition is true, it prints "Unexpected SSH TimeOut."

The `else` statement acts as a fallback, ensuring there's a default action when none of the previous conditions are met. This combination of `if`, `elif`, and `else` makes your code more flexible and able to handle different scenarios.

## Comparison Operators and Conditionals

Comparison operators help you compare values and make decisions in your code. They are essential for creating conditions in your programs.

Here are some common comparison operators:

- `==` (equal)
- `!=` (not equal)
- `<` (less than)
- `>` (greater than)
- `<=` (less than or equal to)
- `>=` (greater than or equal to)

Let's look at the previous example again:

```python
ssh_timeout = 20
if ssh_timeout == 10:
    print("SSH TimeOut: 10 sec")
elif ssh_timeout > 30:
    print("SSH TimeOut Greater Than: 30 sec")
else:
    print("Unexpected SSH TimeOut")
```

In this example, the `==` and `>` operators are used to check if `ssh_timeout` meets certain criteria.

Comparison operators allow you to compare values and create conditions in your code.

## Logical Operators and Conditional Statements

Logical operators help you combine multiple conditions into one expression, making your code's decision-making more complex and powerful.

Here's an example:

```python
ssh_timeout = 20
ip_addr = "10.1.1.1"
host_reachable = True

if host_reachable and ssh_timeout >= 10:
    print("Try to connect")
elif not host_reachable or ip_addr == "10.1.1.1":
    print("Invalid host, do not try connection")
else:
    print("Unexpected error, do something")
```

In this code:

- The `if` statement checks if the host is reachable and the SSH timeout is at least 10 seconds.
- The `elif` statement checks if the host is not reachable or if the IP address is "10.1.1.1".
- The `else` statement handles any other cases.

## Nested Conditional Statements

You can place conditionals inside other conditionals to handle multiple conditions.

Here's an example:

```python
ssh_timeout = 20
host_reachable = True

if host_reachable:
    if ssh_timeout is not None:
        print("Try to connect")
    else:
        print("Unexpected error, do something")
```

In this example:

- The outer `if` checks if the host is reachable.
- The inner `if` checks if `ssh_timeout` is not `None`.

Nested conditionals let you handle complex decision-making in your code.

## Truthy and Falsy Values in Python

In Python, every value is either truthy or falsy. Truthy values are considered `True` in conditions, while falsy values are considered `False`.

Common truthy values:

- Non-zero numbers
- Non-empty strings
- Non-empty collections

Common falsy values:

- `0` (zero)
- `0.0` (zero float)
- `''` (empty string)
- `None` (no value)
- Empty collections (lists, dictionaries, sets)

Here's an example:

```python
ssh_timeout = 0

if not ssh_timeout:
    print("Error, no SSH timeout")
# Output: Error, no SSH timeout
```

In this code, `ssh_timeout` is `0`, a falsy value. The condition `if not ssh_timeout` checks if `ssh_timeout` is falsy, and if it is, it prints "Error, no SSH timeout."

Using truthy and falsy values helps you create flexible and adaptive code.

## Idiomatic Expressions in Python

Idiomatic expressions in Python are about writing code that is clear, efficient, and easy to understand. Using idiomatic expressions improves code readability.

```python
ssh_timeout = 20
ip_addr = None
host_reachable = False

if ssh_timeout is None:  # ssh_timeout == None is not idiomatic
    print("Error, no SSH timeout")
```

- **Idiomatic**: Use `is None` to check if a variable is `None`. This is clearer and more explicit than using `ssh_timeout == None`.

```python
if host_reachable is False:  # host_reachable == False
    print("Error, host is not reachable")
```

Instead of explicitly checking if a boolean variable is `False`, you can use the variable itself in a boolean context. For example, `if not host_reachable:` is more readable than `host_reachable == False`.

```python
if ip_addr is not None:  # ip_addr != None
    print("Error, no SSH timeout")
```

Use `is not None` to check if a variable is not `None`. This is the recommended practice instead of `ip_addr != None`.

Using idiomatic expressions improves code consistency and maintainability. Python linters, which are tools for checking code quality, can help catch non-idiomatic expressions and ensure your code follows best practices.

Conditionals are essential in programming for making decisions, controlling the flow of your code, and handling different scenarios. With comparison and logical operators, you can create dynamic and responsive code that meets various conditions and requirements. Whether dealing with simple choices or complex decision-making, conditionals are a crucial tool in your programming toolkit.
