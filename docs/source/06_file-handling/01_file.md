# Working with Files

This section is focused on how to read and write data from files and update a file.

In this chapter you will learn how to:

- Open files
- Read files
- Write files
- Append to files

## open() function

Before performing any operation on the file like reading or writing, first, we have to open that file. The key function for working with files in Python is the `open()` function. The `open()` function takes two parameters, filename/file-path, and mode. The default opening mode of a file is a read-only mode. There are four different methods (modes) for opening a file:

- "r" - Read - Default mode. Opens a file for reading
- "a" - Append - Opens a file for appending
- "w" - Write - Opens a file for writing
- "x" - Create - Creates the specified file
- "b" - binary mode
- "t" - text mode (default)
- "+" - reading and writing

To open a file for reading it is enough to specify the name or full path of the file:

```py
f = open("my_file.txt", "rt")
```

The code above is the same as:

```py
f = open("my_file.txt")
```

Because `"r"` for read, and `"t"` for text are the default values, you do not need to specify them. If the file does not exist, you will get an error.

## read() Function

When we open a file without setting the mode argument, the default is to open the file in “read-only” mode. The `open()` function returns a file object, which has a `read()` method for reading the content of the file.

```py
f = open("my_file.txt")  # file, located in the same folder
print(f.read())
f.close()  # always close the file when you are done
```

```console
Hello! Welcome to the text file.
This file is for testing purposes only.
```

If the file is located in a different location, you will have to specify the file path. By default, the `read()` method returns the whole text as one big string, but we can return one line by using the `readline()` method.

```py
f = open("my_file.txt")
print(f.readline())  # read the 1st line
print(f.readline())  # read the 2nd line
f.close()
```

```console
Hello! Welcome to the text file.

This file is for testing purposes only.
```

The `readlines()` method will return all the lines in a file in the format of a list where each element is a line in the file with a `\n` character.

```py
f = open("my_file.txt")
print(f.readlines())
f.close()
```

```console
['Hello! Welcome to the text file.\n', 'This file is for testing purposes only.']
```

In Python `read()` method returns the whole text as a *string*, so you can use `splitlines()` method to splits a string into a list. The splitting is done at line breaks.

```py
f = open("my_file.txt")
output = f.read()
print(output.splitlines())
f.close()
```

```console
['Hello! Welcome to the text file.', 'This file is for testing purposes only.']
```

## Write and Create

To write to an existing file, you must add a parameter to the `open()` function.

```py
f = open("my_file.txt", "a") 
f.write("Now more content added to the file.\n")  # '\n' add a new line 
f.close()

f = open("my_file.txt")  # read the file after the append
print(f.read())
f.close()
```

```console
Hello! Welcome to the text file.
This file is for testing purposes only.
Now more content added to the file.
```

```py
f = open("my_file.txt", "w")  # the "w" method will overwrite the entire file
f.write("I have deleted the all content!")
f.close()

f = open("my_file.txt")  # read the file after the write
print(f.read())
f.close()
```

```console
I have deleted the all content!
```

To create a new file in Python, use the `open()` method, with one of the following parameters:

- "x" - create a file, returns an error if the file exists
- "a" - create a file if the specified file does not exist
- "w" - create a file if the specified file does not exist

A new empty file will be created.

```py
f = open("myfile.txt", "x")
```

Create a new file if it does not exist:

```py
f = open("myfile.txt", "w")
```

## File and Context Manager

The best way to open a file in Python is to use Python’s special `with` statement is known as a context manager. In this example, you want to open a file, and then the `with` statement, automatically closes the file.

```py
with open('my_file.txt') as file:
    data = file.read()
    print(data)
```

```console
Hello! Welcome to the text file.
This file is for testing purposes only.
```

## Python’s for loop

You can iterate over a file using Python’s `for` loop, this is actually one of the recommended methods for reading a file.

```py
with open('my_file') as file:
    for line in file:
        print(line)
```

```console
Hello! Welcome to the text file.

This file is for testing purposes only.
```

An alternative way to loop over the lines in a file.

```py
with open('my_file') as file:
    lines = file.readlines()
    for line in lines:
        print(line)
```

### Working with files - network example

In this code, you can iterate over a file of your device's IP list to configure multiple devices. The filename is `device_ip` with the IP address of network devices, as below:

```console
192.168.10.10
192.168.10.11
192.168.10.12
```

Python code:

```py
with open('device_ip') as file:
    for ip in file:
        print(ip)
```

```console
192.168.10.10

192.168.10.11

192.168.10.12
```

For example, you have a configuration file in the same directory from where you have the Python code. The filename is `device_config` with a configuration, like this:

```console
conf ter
int lo 10
ip add 10.10.10.10 255.255.255.255
exit
```

```py
cmd_list = open('device_config')
for ip in cmd_list:
    print(ip)
cmd_list.close()
```

```console
conf ter

int lo 10

ip add 10.10.10.10 255.255.255.255

exit
```
