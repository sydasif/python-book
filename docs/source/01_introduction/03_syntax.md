# Python Syntax

As you learned previously in {ref}`Getting Started`, Python code can be executed by writing directly in the command line/IDLE, or by creating a Python file, using the `.py` file extension, and running it in the command line.

## What is Python Syntax?

The Python syntax defines all the sets of rules that are used to create code in Python programming. You will need to learn and understand the Python syntax in order to learn the Python language.

Python was designed for readability and is similar to English language reading. Python relies on indentation, using whitespace, to define a block of code, such as loops, functions and classes. Blank lines are ignored in Python code when executing the program.

Variables are created dynamically typed, you don’t define the type of the variable. It is assumed on the basis of the value it holds.

## Comments in Python

When writing code you often need to leave a comment, for example, to describe features of the code. Comments in Python can be one-line:

```py
# Important comment read carefully 
username = "admin"
password = "admin123"  # Don't hardcode your password
```

One-line comments start with a `#` sign. Note that the comment can be in-line where the code itself is or in a separate line.

If it is necessary to write several lines of comments in order to not put the `#` sign before each line, we can make a multi-line comment:

```py
"""
This is a multi-line comment in your code
A second-line comment in your code.
"""
a = 14
b = 5
```

Three double or three single quotes may be used for a multi-line comment.

## [Indentation in Python](https://peps.python.org/pep-0008/#indentation)

Indentation refers to the spaces/tabs at the beginning of a code line. While in other programming languages the indentation in code is for readability only, the indentation in Python is very important. Python uses indentation to indicate a block of code.

```py
if 5 > 2:
  print("Five is greater than two!")
```

```console
Five is greater than two!
```

The number of spaces is up to you, but it has to be at least one.

```{Note}
Use 4 spaces per indentation level -- PEP 8
```

```py
if 5 > 2:
  print("Five is greater than two!")  # Example of 2 spaces
```

```console
Five is greater than two!
```

```py
if 5 > 2:
    print("Five is greater than two!")  # Example of 4 spaces 
```

```console
Five is greater than two!
```

You have to use the same number of spaces or tabs in the same block of code, otherwise, Python will give you an error.

```py
if 5 > 2:
  print("Five is greater than two!")  # 2 spaces
    print("Five is greater than two!")  # 4 spaces
```

```console
  Cell In [6], line 4
    print("Five is greater than two!")  # 4 spaces
    ^
IndentationError: unexpected indent
```

Python also gives you an error if you skip the indentation:

```py
if 5 > 2:
print("Five is greater than two!")
```

```console
  Cell In [2], line 4
    print("Five is greater than two!")
    ^
IndentationError: expected an indented block after 'if' statement on line 3
```

## Python Quotations

Python supports the single quote and the double quote for string literals. But if you begin a string with a single quote, you must end it with a single quote. The same goes for double quotes.

```py
print('Hello, World!')
```

```console
Hello, World!
```

This string is delimited by double quotes.

```py
print("Hello, World!")
```

```console
Hello, World!
```

## [Tabs or Spaces?](https://peps.python.org/pep-0008/#tabs-or-spaces)

In Python, spaces are the preferred indentation method. Tabs should be used solely to remain consistent with code that is already indented with tabs. Python disallows mixing tabs and spaces for indentation.

## Error in Python

Everybody makes mistakes, especially while programming, as you see `IndentationError:` in the above code. Mistakes in programs are called errors. You’ll experience two main types of errors, syntax errors and runtime errors.

### Syntax errors

A syntax error occurs when you write code that isn’t allowed in the Python language.

```py
# syntax error "the last quotation mark"
print("Hello, World)
```

```console
  Cell In [2], line 2
    print("Hello, World)
          ^
SyntaxError: unterminated string literal (detected at line 2)
```

The code won’t run! `IDLE` displays an alert box with the above message. `IDLE` highlights the line containing `print("Hello, World)` in red to help you quickly find the line of code with the syntax error.

### Runtime errors

`IDLE` catches syntax errors before a program starts running. In variance, runtime errors only occur while a program is running. To generate a runtime error, remove both quotation marks and save them as the `hello_world.py` file.

```py
print(Hello, World)
```

```console
NameError                                 Traceback (most recent call last)
Cell In [3], line 1
----> 1 print(Hello, World)

NameError: name 'Hello' is not defined
```

Whenever an error occurs, Python stops executing the program and displays several lines of text called a `Traceback`. The `Traceback` shows useful information about the error.
