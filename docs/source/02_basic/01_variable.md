## Variables in Python

A Python variable is like a container that stores data temporarily. You can use this stored data in your code. Variables are essential in any programming language.

- Variables keep values accessible.
- Variables give values meaning.
- Variables make changes easy.
- Variables have data types.

### Variable Declaration

Python is a dynamically typed language, meaning you create a variable by assigning a value to it. You don't need to declare its type, and you can change its type later.

```py
Python 3.12.4 (tags/v3.12.4:8e8a4ba, Jun  6 2024, 19:30:16) [MSC v.1940 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> # Assign a string value to a variable
>>> device_name = "Router1"
>>> # Assign an integer value to a variable
>>> device_port = 22
>>> # Assign a boolean value to a variable
>>> is_connected = True
```

You can find out the data type of a variable using the `type()` function.

```py
>>> ip_addr = "192.168.10.1"
>>> print(type(ip_addr))
<class 'str'>
```

You can assign values to multiple variables in one line.

```py
>>> vlan_01, vlan_10 = "default", "mgmt"
>>> print(vlan_01, vlan_10)
default mgmt
```

You can also assign the same value to multiple variables at once.

```py
>>> host = ip_addr = "192.168.10.1"
>>> print(host, ip_addr)
192.168.10.1 192.168.10.1
```

If you have a list of values, you can extract them into variables.

```py
>>> ip_addr_list = ["10.10.10.10", "172.16.10.10", "192.168.10.10"]
>>> ip_addr1, ip_addr2, ip_addr3 = ip_addr_list
>>> print(ip_addr1)
10.10.10.10
>>> print(ip_addr2)
172.16.10.10
>>> print(ip_addr3)
192.168.10.10
```

### Assignment Statements

An operator is a symbol that performs operations on values. The assignment operator `=` assigns the value on the right to the variable on the left.

```py
>>> hostName = "R-01"
>>> print(hostName)
R-01
```

You can use single or double quotes for string variables.

```py
>>> hostName = "R-01"
>>> print(hostName)
R-01
>>> hostName = 'R-01'
>>> print(hostName)
R-01
```

### Variable Naming Convention

Variable names can be long or short, but there are some rules:

- Must start with a letter or underscore.
- Cannot start with a number.
- Can only contain letters, numbers, and underscores.
- Keywords cannot be used as variable names.
- Variable names are case-sensitive.

```py
>>> # Camel Case - Each word, except the first, starts with a capital letter.
>>> myVariableName = "Alex"
>>> # Pascal Case - Each word starts with a capital letter.
>>> MyVariableName = "Alex"
>>> # Snake Case - Words are separated by underscores.
>>> my_variable_name = "Alex"
```

Use all-caps for constants or configuration values that shouldn't change.

```py
>>> # Define a constant value using all-caps naming convention
>>> MAX_DEVICES = 100
```

Using meaningful variable names like `device_name`, `device_ip`, `device_username`, and `device_password` makes your code more readable and easier to understand.

### Use Descriptive Names

Choose variable names that are descriptive and convey their purpose. Avoid generic names like `temp` or `data`. Instead, use names like `ip_address` or `server_name` to make your code more readable.

### Use Underscores

For multi-word variable names, use underscores to separate words, following the snake_case convention. For example, `device_name` is more readable than `deviceName`.

### Avoid Reserved Words

Be careful not to use Python's reserved words as variable names. For example, naming a variable `print` or `for` can lead to unexpected behavior.

### Consistency

Maintain consistency in your variable naming. If you use `ip_address` in one part of your code, don't switch to `ip_addr` elsewhere. Consistency simplifies code comprehension.

## Python Naming Conventions

Following naming conventions is essential for writing clean and maintainable Python code. Here are some common conventions:

- **snake_case_lower** for variables and functions.
- **PascalCase** for class names.
- **SNAKE_CASE_UPPER** for constants.

Let's dive deeper into these conventions:

### Variable Names

- Start variable names with a lowercase letter or underscore.
- Use clear and descriptive names that convey the variable's purpose.
- For multi-word variable names, use underscores for separation (e.g., `user_id`).

### Function Names

- Begin function names with a lowercase letter or underscore.
- Use descriptive names that hint at the function's action or purpose.
- For multi-word function names, use underscores (e.g., `calculate_speed`).

### Class Names

- Start class names with an uppercase letter.
- Use CamelCase, where each word in the name begins with an uppercase letter and has no underscores (e.g., `NetworkDevice`).

### Constant Names

- Constant variables should be in uppercase with words separated by underscores (e.g., `MAX_CONNECTIONS`).

By following these naming conventions, you'll make your Python code more accessible and comprehensible to yourself and others who collaborate on your projects.
