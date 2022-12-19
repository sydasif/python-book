# String in Python

Python strings are referred to as a sequence of characters/letters that are either literal constants or some kind of variable surrounded by either single quotation marks, or double quotation marks.

The program code below demonstrates the printing of string.

```py
#  variable 'my_str' is a string
my_string = "Network Automation is a fun"
print(my_string)
```

```console
Network Automation is a fun
```

```{epigraph}
In Python, single-quoted strings and double-quoted strings are the same. This PEP does not make a recommendation for this. Pick a rule and stick to it. When a string contains single or double quote characters, however, use the other one to avoid backslashes in the string. It improves readability.

-- PEP 8, *[String Quotes](https://peps.python.org/pep-0008/#string-quotes)*
```

The Python program code below demonstrates a Python function to print the length of the character.

```py
# this code returns the actual length of the string
banner = "Welcome to Network Automation"
print(len(banner))
```

```console
29
```

```{warning}
Don't use the word 'welcome' in any type of banner on a network device.
```
