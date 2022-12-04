# Python Strings

Python strings are referred to as a sequence of characters/letters that are either literal constants or some kind of variable are surrounded by either single quotation marks, or double quotation marks.

The program code below demonstrates the printing the string.

```py
#  variable 'my_str' is a string
my_str = "Network Automation is a fun"
print(my_str)
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
motd_ban = "Welcome to Network Automation"
print(len(motd_ban))
```

```console
29
```

```{warning}
Don't use the word 'welcome' in any type of banner on a network device.
```

## User input in Python

In Python, if we need to interact with users, either to get data input or to provide some sort of result. Asking the user to provide some type of input, Python provides us with built-in `input()` functions to take the input from the keyboard.

This function first takes the input from the user, converts it into a string and store in a variable. It does not evaluate the expression, it just returns the complete statement as String. When the input function is called it stops the program and waits for the user’s input. When the user presses enter, the program resumes and returns what the user has typed.

```py
user = input("Enter your username: ")
print(user)
```

```console
>>> Enter your username: admin
admin
```