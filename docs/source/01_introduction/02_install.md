# [What is Python?](https://www.python.org/about/gettingstarted/)

Python is a clear, powerful and General Purpose object-oriented programming language, comparable to Perl, Ruby, Scheme, or Java. The distinctive feature of Python is that it is an interpreted language.

The Python `IDLE` (Integrated Development Environment) executes instructions one line at a time from top to bottom and left to right.

## Some of Python's Features

Let us now see various features of Python that make it so powerful and popular:

### Easy

Python is very easy to learn and understand. use a neat syntax, making the programs you write easier to read.

### Interpreted

It is interpreted language, executed line by line. This makes it simple to get your program working test and debug.

### Object-Oriented

The Python programming language supports classes and objects and hence it is object-oriented and ideal for prototype development and other ad-hoc programming tasks.

### Free and Open Source

The language and its source code are available to the public for free; It doesn't cost anything to download or use Python, which means there is no need to buy a costly license.

### Portable

Python is open-source, you can run it anywhere, including Mac OS, Windows, Linux or any other platform.

### Large Python Library

Python comes with an extensive standard library that supports many common programming tasks such as connecting to web servers, searching text with regular expressions, and reading and modifying files.

## [Downloading Python](https://www.python.org/downloads/)

Before you start, you will need Python on your computer. Many operating systems, including macOS and Linux, come with Python preinstalled. The version of Python that comes with your operating system is called the system Python. Check whether you already have an up-to-date version of Python installed by entering python in a command line window.

If you see a response from a Python interpreter it will include a version number in its initial display.

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

If you need to install Python, you may download the most recent stable version. This is the one, with the highest number that isn't marked as an alpha or beta release. Please see the [Downloading Python](https://wiki.python.org/moin/BeginnersGuide/Download) for the most up-to-date versions of Python and other operating systems. They are available via the download buttons on that page.

## Getting Started

Python is an interpreted programming language, this means as a developer you write Python `.py` files in a {ref}`Text Editor` and then put those files into the python interpreter to be executed. The way to run a python file is like this on the command line:

```shell
[$] <> python3 hello_world.py
```

Where `hello_world.py` is the name of your python file.

Let's write your first Python file, called `hello_world.py`, which can be done in any {ref}`Text Editor`.

```python
print("Hello, World!")
```

Save your file, open your command line, navigate to the directory where you saved your file, and run the code.

```shell
[$] <> python3 hello_world.py
```

```console
Hello, World!
```

## Command Line

In Python from time to time, it is quickest and easiest not to write the code in a file. This is made possible because Python can be run as a command line itself. Type the following on the Windows, macOS or Linux command line:

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

From there you can write any Python code, including the `Hello, World!` example from earlier in the tutorial:

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

Whenever you are done in the Python command line, you can type the following to quit the Python command line interface:

```shell
[$] <> python3
Python 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> exit() or quit()
```

## The IDLE

You can use the Integrated Development Environment to code in Python. Open the Start menu. Click on IDLE(Python). This will take you to the command prompt for Python. You can now begin coding.

![idle](../images/idle.png)

You can use Python Shell as an interpreter. Otherwise, you can create a new file to write a Python program, save it and click `Run` to run the program.

## Text Editor

Text editors are essential to a programmer, but as a beginner, you only need a simple text editor. Here are some text editors to try:

| Name | OS | Link |
| ----------- | -------- | --------------- |
| Visual Studio Code | Windows, macOS, Linux | [Download](https://code.visualstudio.com/) |
| Notepad++ | Windows | [Download](https://notepad-plus-plus.org/) |
| gEdit | Linux, macOS, Windows | [Download](https://github.com/GNOME/gedit) |

```{seealso}
[Python installation: Windows, Mac and Linux (Kali Linux, Ubuntu) or just run in your browser](https://www.youtube.com/watch?v=LMmtwTV6gTY&t=174s)
```
