# For loops

A `for` loop is used in which the user wants to continuously repeat the execution of a given block of code or statements a known number of times. A `for` loop is used for iterating over a collection (that is either a list, a tuple, a dictionary, a set, or a string). For instance, a `for` loop in Python, is used to run over a specific number of times until a certain condition is reached.

```py
ip_list = ["192.168.10.10", "192.168.10.11", "192.168.10.12"]
for ip in ip_list:
  print(ip)
```

```console
192.168.10.10
192.168.10.11
192.168.10.12
```

## range() Function

The `range()` function returns a sequence of numbers, starting from `0` (default), increments by `1` (default), and stops before a specified number.

```console
range(start, stop, step)
```

```py
x = range(3, 6)
x = range(3, 20, 2)  # increment by 2
```

To loop through a specified number of times, the `range()` function returns a sequence of numbers, `for` loop is used to determine the number of iterations in advance.

```py
for i in range(3):
    print(i)
```

```console
0
1
2
```

The `range()` function defaults to `0` as a starting value, to specify the starting value by adding a parameter; `range(2, 6)`, which means values from `2` to `6` (excluding `6`).

```py
for n in range (2,6):
    print ("VLAN " + str(n))
```

```console
VLAN 2
VLAN 3
VLAN 4
VLAN 5
```

## break and continue statement

With the `break` statement we can stop the loop before it has looped through all the items.

```py
for i in range(10):
    print(i)
    if i == 5:
        break
```

```console
0
1
2
3
4
5
```

Stop the loop when i == 5, but this time the break comes before the print.

```py
for i in range(10):
    if i == 5:
        break
    print(i)
```

```console
0
1
2
3
4
```

With the `continue` statement we can stop the current iteration of the loop, and continue with the next.

```py
for i in range(5):
    if i == 2:  # 2 will skip in iteration
        continue
    print(i)
```

```console
0
1
3
4
```

A nested loop is a loop inside a loop. The "inner loop" will be executed one time for each iteration of the "outer loop".

```py
ip_list = ['1.1.1.1', '2.2.2.2', '3.3.3.3']  # list
netmask = ("255.255.255.255",)  # tuple
for ip in ip_list:
    for mask in netmask:
        print(f'ip address {ip} {mask}')
```

```console
ip address 1.1.1.1 255.255.255.255
ip address 2.2.2.2 255.255.255.255
ip address 3.3.3.3 255.255.255.255
```

### For loop - network example

In this code, you can iterate over a list of your device IP.

```py
# IP list fo network device
devices =['192.168.10.11', '192.168.10.12']

# For loop and list to connect multiple devices
for device in devices:
    print ('#### Connecting to the device ' + device + ' ####\n' )
```

```console
#### Connecting to the device 192.168.10.11 ####

#### Connecting to the device 192.168.10.12 ####
```

For loop and `range()` function to create configuration template.

```py
for num in range (0,2):
    print('int lo ' + str(num) + '\n')
    print('ip address 1.1.1.' + str(num) + ' 255.255.255.255\n')
```

```console
int lo 0
ip address 1.1.1.0 255.255.255.255
int lo 1
ip address 1.1.1.1 255.255.255.255
```
