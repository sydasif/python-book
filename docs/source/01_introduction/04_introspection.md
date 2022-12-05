# Introspection in Python

In programming, the ability to examine classes, functions and keywords to know what they are, what they can do and what they know. Python provides several functions and utilities for code self-examination. Python provides lots of tools that allow you to learn about it. There are several built-in functions that you can use to learn about the code, as below:

- The `type()` function
- The `dir()` function
- The `help()` function

## type() Function

When you are working with code, it can be useful to check and see what data type it is. Is the code a string, an integer or some kind of object? This is especially useful when you are working with code that you have never used before.

This is where using the `type()` function can be valuable.

```py

a = 10
b = 10.5
c = True
d = 1 + 5j

print(type(a))
print(type(b))
print(type(c))
print(type(d))
```

```console
<class 'int'>
<class 'float'>
<class 'bool'>
<class 'complex'>
```

## dir() method

The Python `dir()` method returns the list of valid attributes of the passed object as below:

The syntax of the `dir()` method is `dir('object')`.

- **object** can be an empty/filled tuple, list, set, dictionary etc or any user-defined object.

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> dir(list)
['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
>>>
```

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> dir(str)
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
>>> 
```

## help() function

The Python `help()` function is used to display the documentation of modules, functions, classes, keywords, etc. The help function has the following syntax:

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> help('print')
```

```console
Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
    
    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.

```

If the `help()` function is passed without an argument, then the interactive help utility starts up on the console.

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> help()
```

```console
Welcome to Python 3.8's help utility!

If this is your first time using Python, you should definitely check out
the tutorial on the Internet at https://docs.python.org/3.8/tutorial/.

Enter the name of any module, keyword, or topic to get help on writing
Python programs and using Python modules.  To quit this help utility and
return to the interpreter, just type "quit".

To get a list of available modules, keywords, symbols, or topics, type
"modules", "keywords", "symbols", or "topics".  Each module also comes
with a one-line summary of what it does; to list the modules whose name
or summary contain a given string such as "spam", type "modules spam".

help> 
```

The `help()` function has the following syntax to check the module.

```console
help> telnetlib
Help on module telnetlib:

NAME
    telnetlib - TELNET client class.

MODULE REFERENCE
    https://docs.python.org/3.8/library/telnetlib
    
    The following documentation is automatically generated from the Python
    source files.  It may be incomplete, incorrect or include features that
    are considered implementation detail and may vary between Python
    implementations.  When in doubt, consult the module reference at the
    location listed above.

DESCRIPTION
    Based on RFC 854: TELNET Protocol Specification, by J. Postel and
    J. Reynolds
    
    Example:
    
    >>> from telnetlib import Telnet
    >>> tn = Telnet('www.python.org', 79)   # connect to finger port
    >>> tn.write(b'guido\r\n')
    >>> print(tn.read_all())
```

## [pydoc](https://docs.python.org/3/library/pydoc.html#module-pydoc) — Documentation generator and online help

The `pydoc` module automatically generates documentation from Python modules. The documentation can be presented as pages of text on the console, served to a web browser, or saved to HTML files.

The built-in function `help()` invokes the online help system in the interactive interpreter, which uses `pydoc` to generate its documentation as text on the console. The same text documentation can also be viewed from outside the Python interpreter by running pydoc as a script at the operating system’s command prompt. For example, running

```console
pydoc sys
```

A shell prompt will display documentation on the `sys` module, in a style similar to the manual pages shown by the Unix/Linux man command.
