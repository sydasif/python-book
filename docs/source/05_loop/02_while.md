# While loop

The `while` loop is another kind of a loop structure in Python. The `while` loop executes a given block of code repeatedly if certain requirements are met or based on a boolean condition and stop the `while` loop when the condition is false.

With the `while` loop we can execute a set of statements as long as a condition is `True`.

```py
i = 1
while i < 5:
    print(i)
    i += 1
```

```console
1
2
3
4
```

Basic rules for using the `while` loop:

- Initialized the variables.
- While the loop executes, update the variable.
- The code at some time return a `False` condition to avoid an infinite loop.

With the break statement we can stop the loop even if the while condition is `True`.

```py
i = 1

while True:
    print(i)
    i = i + 1
    if i > 5:
        break
```

```console
1
2
3
4
5
```

With the continue statement we can stop the current iteration, and continue with the next.

```py
i = 0

while i < 5:
  i += 1
  if i == 3:
    continue  # skip to next if i == 3
  print(i)
```

```console
1
2
4
5
```

## Usage of For and While loop

**For loop** If you know, prior to the start of loop, how many times you want to repeat the loop.

**While loop** If you don’t know of a certain number of runs and a set of conditions are to be met.

```py
age = 20
person_age = int(input("Enter your age: "))

while person_age in range(0, 30):
    if person_age <= 17:
        print("You are not allowed.")
        break
    if person_age >= 18:
        print("You are allowed.")
        break
```

```console
You are allowed.
```
