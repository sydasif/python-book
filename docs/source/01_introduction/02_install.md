# What is Python?

Python is a clear and powerful object-oriented programming language, comparable to Perl, Ruby, Scheme, or Java.

## Some of Python's notable features

- Uses an elegant syntax, making the programs you write easier to read.
- Is an easy-to-use language that makes it simple to get your program working.
- Python is ideal for prototype development and other ad-hoc programming tasks.
- Comes with a large standard library that supports many common programming tasks such as connecting to web servers, searching text with regular expressions, and reading and modifying files.
- Python's interactive mode makes it easy to test short snippets of code.
- Runs anywhere, including Mac OS, Windows, Linux, and Unix.
- Is free software in two senses. It doesn't cost anything to download or use Python.

### Some programming-language features of Python

- A variety of basic data types are available; numbers, lists and dictionaries.
- Python supports object-oriented programming with classes and multiple inheritances.
- Code can be grouped into modules and packages.
- The language supports raising and catching exceptions, resulting in cleaner error handling.
- Python contains advanced programming features such as generators and list comprehensions.

## [Downloading Python](https://www.python.org/downloads/)

Before you start, you will need Python on your computer. Many operating systems, including macOS and Linux, come with Python preinstalled. The version of Python that comes with your operating system is called the system Python. Check whether you already have an up-to-date version of Python installed by entering python in a command line window.

If you see a response from a Python interpreter it will include a version number in its initial display.

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

If you need to install Python, you may as well download the most recent stable version. This is the one with the highest number that isn't marked as an alpha or beta release. Please see the [Downloading Python](https://wiki.python.org/moin/BeginnersGuide/Download) for the most up-to-date versions of Python and other operating systems. They are available via the yellow download buttons on that page.

## [Getting Started with Python](https://www.python.org/about/gettingstarted/)

Python is an interpreted programming language, this means as a developer you write Python `.py` files in a text editor and then put those files into the python interpreter to be executed. The way to run a python file is like this on the command line:

```shell
[$] <> python3 hello_world.py
```

Where `hello_world.py` is the name of your python file.

Let's write our first Python file, called `hello_world.py`, which can be done in any text editor.

```python
print("Hello, World!")
```

Save your file, open your command line, navigate to the directory where you saved your file, and run.

```shell
[$] <> python3 hello_world.py
```

The output should read:

```console
Hello, World!
```

## Python Command Line

In python sometimes it is quickest and easiest not to write the code in a file. This is made possible because Python can be run as a command line itself. Type the following on the Windows, Mac or Linux command line:

```shell
[$] <> python3
```

From there you can write any `python`, including our hello world example from earlier in the tutorial:

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print("Hello, World!")
```

Which will write `Hello, World!` in the command line:

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print("Hello, World!")
Hello, World!
```

Whenever you are done in the python command line, you can simply type the following to quit the python command line interface:

```console
[$] <> exit()
```

or

```console
[$] <> quit()
```

```{seealso}
- [How to Install Python on Windows](https://realpython.com/installing-python/#how-to-install-python-on-windows)
- [How to Install Python on Linux](https://realpython.com/installing-python/#how-to-install-python-on-linux)
- [How to Install Python on macOS](https://realpython.com/installing-python/#how-to-install-python-on-macos)
- [See more information about Python](https://www.python.org/about/gettingstarted/)
```
