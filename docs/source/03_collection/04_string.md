# [String in Python](https://developers.google.com/edu/python/strings?__s=tzcymf3pqbdij8ldw40h)

A string is a collection of characters/letters, in other terms characters are simple letters and symbols that are used
to make a string and characters include alphanumeric letters, numbers and whitespace.

In Python, strings are written and enclosed between either `single` or `double` quotes. Once a string variable has been
created and declared, it is impossible to change its values, unless a new string is created. Assigning a string to a
variable is done with the variable name followed by an equal sign `=` and the string.

```py
intf = 'FastEthernet1/0'
print(intf)
```

```console
FastEthernet1/0
```

Using `triple` quotes allows the creation of multi-line strings. Any whitespace within the string will also be included.

```py
intf_ip = """
interface FastEthernet1/0
 ip address 172.16.10.1 255.255.255.0
"""
print(intf_ip)
```

```console
interface FastEthernet1/0
 ip address 172.16.10.1 255.255.255.0
```

## String Slicing

There are various ways of manipulating a string using the slicing method, which works the same way that it does for a list.

```py
intf = "interface FastEthernet1/0"
print(intf[0:9])
print(intf[10:])
```

```console
interface
FastEthernet1/0
```

## String Concatenation

Strings allow concatenation for joining two strings into one or combine text with numbers.

### Addition

The `+` operator allows the user to put together two strings to come up with the third string.

```py
intf = "interface"
intf_name = "FastEthernet0/1"
cmd = intf + " " + intf_name
print(cmd)
```

```console
interface FastEthernet0/1
```

### String Replication

The nice thing about the multiplication operator `*` is that it’s also possible to use it on strings. For example,
to print a line of `60` dashes.

```py
print("#" * 60)
```

```console
############################################################
```

## String Method

Python has a set of built-in methods that you can use on strings.

```{Note}
All string methods return new values. They do not change the original string.
```

```py
# methods lower(), upper(), isdigit() and startswith()
vendor = "Samsung Ltd"
print(vendor.upper())  # Upper case 
print(vendor.lower())  # lower case
```

```console
SAMSUNG LTD
samsung ltd
```

### strip() method

You will find that the `strip()`, `split()` and `splitlines()` methods are especially useful when parsing or
manipulating text from a network device.

If you have the value of text " 192.168.10.10 " including the whitespace. The methods `startswith()` or `endswith()`
do not work because of the spaces. To remove the whitespace from this value, `strip()` method is used.

```shell
>>> ipaddr = ' 192.168.10.10 '
>>> ipaddr
' 192.168.10.10 '  
>>> ipaddr.strip()
'192.168.10.10'
```

### split() method

Return a list of the substrings in the string:

```py
motd_banner = 'This router is configured by Python script'
print(motd_banner.split())  # The result is a list
```

```console
['This', 'router', 'is', 'configured', 'by', 'Python', 'script']
```

### splitlines() method

The `splitlines()` method splits a string into a list, where each line is a list item. The splitting is done at line breaks:

```py
my_text = """Welcome to the Network Automation.
Thank you Python...
"""

text = my_text.splitlines()

print(text)
```

```console
['Welcome to the Network Automation.', 'Thank you Python...']
```

To get a full listing of the methods and attributes that you can access, you can use Python’s built-in {ref}`dir() Function`

````{epigraph}
To learn how to use a given method that you see in the output of a dir(). Use the built-in help() function,
the following examples show the way you can use help() method:

```console
[$] <> python
Python 3.10.7 (tags/v3.10.7:6cc6b13, Sep  5 2022, 14:08:36)
>>> help(str.split)
Help on method_descriptor:

split(self, /, sep=None, maxsplit=-1)
    Return a list of the substrings in the string, using 
    sep as the separator string.

Output is Omitted
```
````

### join() method

The `join()` method takes all items in an iterable (e.g. list/tuple) and joins them into one string. A string must be
specified as the separator.

```py
motd_str = ["Python", "Network", "Automation"]
motd_banner = "#".join(motd_str)
print(motd_banner)
```

```console
Python#Network#Automation
```

## Escape Sequences

There is a special character, that is understood by the compiler as commands other than characters. All these characters
are known as the `escape` sequences. The special characters are marked with a backslash `\`. The backslash `\` would,
therefore, indicate that the character that is going to be printed next is a special one that should initiate some
instructions. Below are examples of special characters that are used with strings:

- `\n` Newline
- `\t` Horizontal tab
- `\r` Carriage return
- `\b` Backslash

## Raw String

To avoid special processing on a string such as `escape` sequences. Specify a raw string by prefixing `r` or `R` to the
string.

```py
string = r"newline is indicated by \n."
print(string)
```

```console
newline is indicated by \n.
```
## String Formatting

String formatting or string substitution is where you have a string that you would like to insert into another string.

Python has three different ways to accomplish string formatting:

- Using the `%` Method
- Using `format()`
- Using formatted string literals (`f-strings`)

### Formatting string using `%`

Using the `%` method is Python’s oldest method of string formatting. The most common use of using the % sign is when
you would use `%s`, which means converting any Python object to a string using `str()`.

```py
ip_addr = "172.16.10.1"
print("IP Address: %s" %ip_addr)  # insert string
```

```console
IP Address: 172.16.10.1
```

```py
ios_version = 15
print("iOS Version: %i" %ios_version)  # insert integer
```

```console
iOS Version: 15
```

```py
ip_addr = "172.16.10.1"
mask = "255.255.255.0"
# formatting with multiple variables
print("IP Address: %s. Mask: %s" %(ip_addr, mask))
```

```console
IP Address: 172.16.10.1. Mask: 255.255.255.0
```

To pass in multiple items, you use the `%` sign followed by a tuple of the items to insert.

### Formatting string using format()

The `format()` method formats the specified value(s) and insert them inside the string's placeholder. The placeholder
is defined using curly brackets: `{}`. The `format()` method returns the formatted string.

```py
ip_addr = "172.16.10.1"
mask = "255.255.255.0"
print("IP Address: {} Mask: {}".format(ip_addr, mask))
```

```console
IP Address: 172.16.10.1 Mask: 255.255.255.0
```

This example uses positional arguments. Python looks for two instances of `{}` and will insert the variables accordingly.

```py
ip_addr = "172.16.10.1"
subnet = "255.255.255.0"
print("IP Address: {ip} Mask: {mask}".format(ip=ip_addr, mask=subnet))
```

```console
IP Address: 172.16.10.1 Mask: 255.255.255.0
```

- Using dictionary

```py
credentials = {"user": "admin", "pass": "P@ssW0rd"}
print("Username: {user} \nPassword: {pass}".format(**credentials))
```

```console
Username: admin 
Password: P@ssW0rd
```

A common coding style when working with `format()` is to create a formatted string and save it to a variable to 
be used later.

```py
description = """
Device: {}
IP: {}
"""
output = description.format('SW-01', '10.10.10.10')
print(output)
```

```console
Device: SW-01
IP: 10.10.10.10
```

### Formatting string with f-strings

Formatted string literals or `f-strings` are strings that have an `f` at the beginning and curly braces inside of them
that contain expressions, much like the ones you saw in the previous section.

```py
ip_addr = '172.16.10.1'
mask = "255.255.255.0"
print(f'IP Address {ip_addr} Mask: {mask}')
```

```console
IP Address 172.16.10.1 Mask: 255.255.255.0
```

The `f-string` can do things that neither `%s` nor `format()` can do. Because `f-strings` are evaluated at runtime,
you can put any valid Python expression inside of them.

```py
age = 25
print(f"{age + 5}")
```

```console
30
```

One more example as below:

```py
name = 'Ali'
print(f'{name.lower()}') # call a method or function
```

```console
ali
```

```{Note}
The `f-string` was added in Python 3.6.
```

```{seealso}
- For more info see [website](https://docs.python.org/3/library/stdtypes.html#printf-style-string-formatting).
- You can read more about it and how it works by checking out [PEP 498](https://www.python.org/dev/peps/pep-0498/).
- For more info see python [doc](https://docs.python.org/3/library/string.html#formatstrings).
```
