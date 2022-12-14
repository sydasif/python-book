# Exceptions in Python

An exception is usually an event, that may not be an error that occurs during the code execution and stop the normal flow of that program. Python as a programming language raises an exception if the Python scripts met such a situation.

To make the script better, your code needs to keep working even when the unexpected happens. For example, let’s say your application needs to pull down information from the router, what happens if your application loses its connectivity?

Another common issue is what to do if the user enters invalid input or tries to open a file that is not present or deleted. support.

## Exceptons Handling

Python comes with a special syntax that you can use to catch an exception. It is known as the `try/except` statement.

```py
try:
  print(x)
except NameError:
  print("Vaiable 'x' is not defined")
```

```console
Vaiable 'x' is not defined
```

Since the `try` block raises an error, the `except` block will be executed. Without the `try` block, the program will crash and raise an error.

```{Note}
When you write the `except` without specifying the exception type, it is known as a bare exception, it is not recommended.
```

To catch multiple exceptions. Here is one way to do that:

```py
x = '1'
y = 2

try:
  z = x + y
  print(z)
except:
  print("Something wrong")
```

```console
Something wrong
```

## finally Statement

There is more to the `try/except` statement than just `try` and `except`. You can add a `finally` statement to it as well. The `finally` statement is a block of code that will always get run even if there is an exception raised inside of the `try` portion. You can use the `finally` statement for cleanup.To do that, you can wrap the code in a try/except/finally statement.

```py
try:
  1 / 0
except ZeroDivisionError:
  print('You can not divide by zero!')
finally:
  print('try/except block end.')
```

```console
You can not divide by zero!
try/except block end.
```

```{Note}
You can also skip the `except` statement entirely and create a try/finally
```

## else Statement

There is one other statement that you can use with Python’s exception handling and that is the `else` statement. You can use the `else` statement to execute code when there are no exceptions.

```py
try:
  print("Hello")
except:
  print("Something went wrong")
else:
  print("Nothing went wrong")
```

```console
Hello
Nothing went wrong
```

```{seealso}
Full listing of the built-in exceptions, on Python [documentation](https://docs.python.org/3/library/exceptions.html).
```
