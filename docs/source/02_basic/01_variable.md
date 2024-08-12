## Variables in Python

A Python variable is like a container that stores data temporarily. You can use this stored data in your code. Variables are essential in any programming language.

- Variables keep values accessible.
- Variables give values meaning.
- Variables make changes easy.
- Variables have data types.

### Variable Declaration

Python is a dynamically typed language, meaning you create a variable by assigning a value to it. You don't need to declare its type, and you can change its type later.

```py
# Assign a string value to a variable
device_name = "Router1"

# Assign an integer value to a variable
device_port = 22

# Assign a boolean value to a variable
is_connected = True
```

You can find out the data type of a variable using the `type()` function.

```py
ip_addr = "192.168.10.1"
print(type(ip_addr))
```

```console
<class 'str'>
```

You can assign values to multiple variables in one line.

```py
vlan_01, vlan_10 = "default", "mgmt"
print(vlan_01, vlan_10)
```

```console
default mgmt
```

You can also assign the same value to multiple variables at once.

```py
host = ip_addr = "192.168.10.1"
print(host, ip_addr)
```

```console
192.168.10.1 192.168.10.1
```

If you have a list of values, you can extract them into variables.

```py
ip_addr_list = ["10.10.10.10", "172.16.10.10", "192.168.10.10"]

ip_addr1, ip_addr2, ip_addr3 = ip_addr_list

print(ip_addr1)
print(ip_addr2)
print(ip_addr3)
```

```console
10.10.10.10
172.16.10.10
192.168.10.10
```

### Assignment Statements

An operator is a symbol that performs operations on values. The assignment operator `=` assigns the value on the right to the variable on the left.

```py
hostName = "R-01"
print(hostName)
```

```console
R-01
```

You can use single or double quotes for string variables.

```py
hostName = "R-01"
print(hostName)
```

```console
R-01
```

```py
hostName = 'R-01'
print(hostName)
```

```console
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
# Camel Case - Each word, except the first, starts with a capital letter.
myVariableName = "Alex"
# Pascal Case - Each word starts with a capital letter.
MyVariableName = "Alex"
# Snake Case - Words are separated by underscores.
my_variable_name = "Alex"
```

Use all-caps for constants or configuration values that shouldn't change.

```py
# Define a constant value using all-caps naming convention
MAX_DEVICES = 100
```

Using meaningful variable names like `device_name`, `device_ip`, `device_username`, and `device_password` makes your code more readable and easier to understand.
