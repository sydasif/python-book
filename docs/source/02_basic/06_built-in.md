# Built in Function

Python has several functions that are readily available for use. These functions are called built-in functions.

## Some Buitl-in Functions

### print() function

A `print()` statement can take any number of arguments and output them separated with a space to the console.

```py
print("Hello", 10, 3.5)
```

```console
Hello 10 3.5
```

### len() function

You can pass the `len()` function to a string value (or a variable containing a string), and the function evaluates to the integer value of the number of characters in that string.

```py
len('hello')
```

```console
5
```

### input() function

If you need to interact with user, either to get data input or to provide some sort of result. Asking the user to provide some type of input, Python provides us with built-in `input()` functions to take the input from the keyboard.

This function first takes the input from the user, converts it into a string and stores it in a variable. It does not evaluate the expression; it just returns the complete statement as string. When the `input()` function is called it stops the program and waits for the user’s input. When the user presses `enter`, the program resumes and returns what the user has typed.

You can prompt the user to input a string and assign it to a variable.

```py
user = input("What is your name? ")
print(user)
```

```console
>>> What is your name? Ali
Ali
```

### bin() function

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

### oct() function

The `oct()` function takes an integer number and returns its octal representation.

```py
num = 100
print(oct(num))  # print octal number
```

```console
0o144
```

The `oct()` function returns an octal string from the given integer number.

### hex() function

The `hex()` function converts an integer number to the corresponding hexadecimal string. The `hex()` function converts an integer to the corresponding hexadecimal number in string form and returns it.

```py
num = 100
print(hex(num))  # print hex number
```

```console
0x64
```

The returned hexadecimal string starts with the prefix 0x indicating it's in hexadecimal.

### round() function

The `round()` function returns a floating point number that is a rounded version of the specified number, with the specified number of decimals.

```py
num = round(5.12345, 2)
print(num)
```

```console
5.12
```

### id() function

All objects in Python when created, has its own unique id (memory location), the `id()` function returns a unique id of the specified object.

```py
num = 5.12
id(num)
```

```console
1707832475504
```

The id is the object's memory address, and will be different for each time you run the program. (except for some object that has a constant unique id, like integers from `-5` to `256`).
