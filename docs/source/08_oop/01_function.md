# Function in Python

There is some piece of code that has been organized into a block and can be reused more than once for a single related task. These blocks of code are functions in Python. They provide reusing of program codes, and creating a customized function is easy in Python. We defined a function in Python using the `def` keyword.

```py
def my_function():  # Creating a Function
  print("Hello, Ali your age is 13 years.")


my_function()  # Calling a Function
```

```console
Hello, Ali your age is 13 years.
```

Functions begin with the keyword `def`, then followed by the name of the function and parenthesis. The parenthesis takes all the input parameters and the code block in every function begins after a colon. To call a function, use the function name followed by a parenthesis.

There are two types of functions in Python:

- Built-in Functions
- User-defined Functions

Built-in functions are those functions that have been pre-written with the Python language and contained in the libraries. Python language has several built-in functions that are reused over and over making it easy to perform similar tasks without necessarily writing the code from scratch. For example, Python has many built-in functions, such as `dir()` and `sum()`.

Python language allows a declaration of functions, these functions are called user-defined functions and are created by the programmer during the code.

## Return Values

Python automatically returns `None` value if you do not specify a return value. Let’s try calling the function and assigning its result to a variable.

```py
def my_function(num):
    print(5 + num)

add = my_function(3)
print(add)
```

```console
8
None
```

To let a function return a value, we use the `return` statement.

```py
def my_function(num):
    return 5 + num


add = my_function(3)
print(add)
```

```console
8
```

## Function Arguments

In most functions, let you pass in arguments to them. The reason for this is that you will normally want to pass one or more arguments to a function, so that the function can do something with them.

In Python, the terms `parameter` and `argument` are used interchangeably. However, there is a diffrence between these two terms. Parameters are the variables when defining a function, whereas arguments are the values assigned to these parameters when passed into a function during a function call.

### Positional arguments

Positional arguments are values that are passed into a function based on the order in which the parameters were listed during the function definition. The order is especially important as values passed into these functions are assigned to corresponding parameters based on their position.

The following example has a function with one positional argument `name`. When the function is called, we pass along a name, which is used inside the function to print the greeting.

```py
def greeting(name):
    print(f"Hello, {name}")

greeting("Ali")
```

```console
Hello, Ali
```

Arguments are specified after the function name, inside the parentheses. You can add as many positional arguments as you want, just separate them with a comma.

### Default arguments

Default arguments are a way to make your function callable with less arguments, whereas required arguments are ones that you have to pass in to the function for the function to execute a task.

```py
def greeting(name, age: int=5):
    print(f"Welcome {name}. You are {age} years old.")

greeting("Ali")
```

```console
Welcome Ali. You are 5 years old.
```

In the above example, a regular argument `name` and a default argument, `age` which is a defaulte value to `5`. When we call this code without specifying the `age`, we see it defaults to `5`.

```py
def greeting(name, age: int=5):
    print(f"Welcome {name}. You are {age} years old.")

greeting("Ali", age=10)
```

```console
Welcome Ali. You are 10 years old.
```

In this example, we specified `age` and `name` parameters. When we do that, you can specify positional argument first in order,as positional argument followed by a keyword argument. If we pass in values without specifying where they should go, they will be passed in order.

### Keyword (named) arguments

You can also send arguments with the `key=value` syntax. This way the order of the arguments does not matter.

```py

def my_function(child2, child1):
  print("The youngest child is " + child2)
  print("The older child is", child1)

my_function(child1="Ali", child2="Toba")
```

```console
The youngest child is Toba
The older child is Ali
```

With keyword arguments, as long as you assign a value to the parameter, the positions of the arguments do not matter. However, they do have to come after positional arguments and before default arguments in a function call.

### args and kwargs in function

In Python function, we want that our functions to only accept a small number of arguments, keyword arguments or both. We normally don’t want too many arguments as it becomes more complicated to modify our function later. However, Python supports the concept of any number of arguments or keyword arguments.

- *args - An arbitrary number of arguments
- **kwargs - An arbitrary number of keyword arguments

```{Note}
We need to pay attention to the `*` and the `**`, the name, `arg` or `kwarg` can be anything.
```

```py
def my_function(*args):
  print(args)

my_function(1, 2, 3)
```

```console
(1, 2, 3)
```

If you do not know how many keyword arguments that will be passed into your function, add two asterisk `**` before the parameter name in the function.

```py
def my_function(**kwargs):
  print(kwargs)

my_function(f_name = "Ali", l_name = "Ahmed")
```

```console
{'f_name': 'Ali', 'l_name': 'Ahmed'}
```

If we created the function to accept keyword arguments only but we passed in normal arguments. This caused a `TypeError` to be thrown. Now let’s inspect our `*args` and `**kwargs` and see what they are:

```py
def check_type(*args, **kwargs):
    print("*args is:", type(args))
    print("**kwargs is:", type(kwargs))

check_type()
```

```console
*args is: <class 'tuple'>
**kwargs is: <class 'dict'>
```

```{Note}
*args* is a tuple and *kwargs* are a dictionary.
```

Let’s see if we can pass our function a `tuple` and `dict` for the `*args` and `**kwargs`:

- Pass in tuple as argument:

```py
my_tuple = (1, 2, 3)

def tup_output(*args):
    print(args)

tup_output(*my_tuple)
```

```console
((1, 2, 3),)
```

With `*my_tuple`, Python extract the individual values in the tuple and pass each of them in as arguments.

- Pass in dictionary as keyword argument:

```py
my_dict = {'one': 1, 'two': 2}

def dict_output(**kwargs):
    print(kwargs)

dict_output(**my_dict)
```

```console
{'one': 1, 'two': 2}
```

With `**my_dict`, tells Python to pass in each `key=value` pair as keyword arguments.

## Scope of Variables

In Python, variables have different scopes depending on their location in the code. Variables can be either `local` or `global`. A `local` variable is referred to those, that are declared within a function. Global variables are that, declared outside of the function at the script and accessible from anywhere in the program including functions.

### Global variables

Global variables are declared in Python scripts outside of any function. These variables are accessible anywhere in the code including functions within the Python program code. The example below shows a variable named `a` that has been created at the top of the function and is accessible from anywhere in the program code.

```py
a = 5

def num():
    print(a)

num()

print(a)
```

```console
5
5
```

### Local variables

Loacl variables are declared inside of a functions. These variables are only accessible within the functions where they are declared. These variables cannot be used/accessed on other parts of the program code except within the functions.

```py
a = 5

def num():
    b = 3
    print(b)

num()

print(a)
```

If we call variable `b` outside from function it will give an `NameError:` name 'b' is not defined.
