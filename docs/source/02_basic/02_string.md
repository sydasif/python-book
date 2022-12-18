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

## len() Function

You can pass the `len()` function to a string value (or a variable containing a string), and the function evaluates to the integer value of the number of characters in that string.

```py
len('hello')
```

```console
5
```

## input() Function

If you need to interact with user, either to get data input or to provide some sort of result. Asking the user to provide some type of input, Python provides us with built-in `input()` functions to take the input from the keyboard.

This function first takes the input from the user, converts it into a string and stores it in a variable. It does not evaluate the expression; it just returns the complete statement as string. When the `input()` function is called it stops the program and waits for the user’s input. When the user presses `enter`, the program resumes and returns what the user has typed.

You can prompt the user to input a string and assign it a variable.

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> input()
```

You can prompt a question with the `input()` statement.

```py
user = input("What is your name? ")
print(user)
```

```console
>>> What is your name? Ali
Ali
```

## bin() in Python

The `bin()` method converts an integer to its binary value and returns it.

```py
num = 100
print(bin(num))  # print binary number
```

```console
0b1100100
```

The `bin()` method returns, the binary string equivalent to the given integer and `TypeError` for a non-integer argument.

```{Note}
The prefix `0b` in the output `0b1100100` represents that the result is a binary string.
```

## oct() in Python

The `oct()` function takes an integer number and returns its octal representation.

```py
num = 100
print(oct(num))  # print octal number
```

```console
0o144
```

The `oct()` function returns an octal string from the given integer number.

## hex() in Python

The `hex()` function converts an integer number to the corresponding hexadecimal string. The `hex()` function converts an integer to the corresponding hexadecimal number in string form and returns it.

```py
num = 100
print(hex(num))  # print hex number
```

```console
0x64
```

The returned hexadecimal string starts with the prefix 0x indicating it's in hexadecimal form.
