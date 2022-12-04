# Testing Network Connection

In this section, we test our lab to connect to network devices with Python script via:

- Telnet
- SSH

## Telnet to the Router

**Telnet**  is a type of network protocol that allows users on the Internet/local area networks to provide a bidirectional interactive text-oriented communication using a virtual terminal connection, to another device.

The telnet command is used along with the hostname and then the user credentials are entered. Telnet sends commands and retrieves data from the remote devices in plain text, anyone watching your Telnet packets on the wire will see your username, password, and everything you do on the remote system, so it is recommended that it not be used in the production environment.

### telnetlib Module

The telnetlib is a Python module, that provides a `Telnet()` class that implements the Telnet protocol. Python’s telnetlib lets you easily automate access to Telnet servers (device), even from non-Unix machines. The telnetlib library is already included in the python package.

```{Note}
telnetlib has deprecated since version 3.11, will be removed in version 3.13
```

With Python 'help()' function we check the 'telnetlib' module doc:

```console
>>> help('telnetlib')
Help on module telnetlib:

# Output is Omitted

    Example:

    >>> from telnetlib import Telnet
    >>> tn = Telnet('www.python.org', 79)   # connect to finger port
    >>> tn.write(b'guido\r\n')
    >>> print(tn.read_all())
    Login       Name               TTY         Idle    When    Where
    guido    Guido van Rossum      pts/2        <Dec  2 11:10> snag.cnri.reston.
```

From the above output copy the example and amend it as below:

```py
from telnetlib import Telnet
tn = Telnet('192.168.10.11')   # connect to finger port
tn.write(b'admin\n')  # Username
tn.write(b'cisco\n')  # Password
tn.write(b'sh ip int bri\n')  # Cisco router cmd
tn.write(b'exit\n')  # Cisco router cmd
print(tn.read_all())  # Print the output
```

Output

```console
root@NetworkAutomation-1:~# python3 01_basic_script.py
b'\r\n\r\nUser Access Verification\r\n\r\nUsername: admin\r\nPassword: \r\nR1>sh ip int bri\r\nInterface                  IP-Address      OK? Method Status                Protocol\r\nFastEthernet0/0            192.168.10.11   YES NVRAM  up                    up      \r\nFastEthernet0/1            unassigned      YES NVRAM  administratively down down    \r\nR1>exit\r\n'
root@NetworkAutomation-1:~#
```

The above text in byte string is difficult to understand by humans, to make it human readable we need to convert it in plain text string.

```{margin} **How does ASCII work?**

ASCII offers a universally accepted and understood character set for basic data communications. It enables developers to design interfaces that both humans and computers understand. ASCII codes a string of data as ASCII characters that can be interpreted and displayed as readable plain text for people and as data for computers.

Programmers use the design of the ASCII character set to simplify certain tasks. For example, using ASCII character codes, changing a single bit easily converts text from uppercase to lowercase.
```

```py
from telnetlib import Telnet
tn = Telnet('192.168.10.11')   # connect to finger port
tn.write(b'admin\n')  # Username
tn.write(b'cisco\n')  # Password
tn.write(b'sh ip int bri\n')  # Cisco router cmd
tn.write(b'exit\n')  # Cisco router cmd
print(tn.read_all().decode('ascii'))  # Print the output
```

Output

```console
root@NetworkAutomation-1:~# python3 01_basic_script.py


User Access Verification

Username: admin
Password:
R1>sh ip int bri
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            192.168.10.11   YES NVRAM  up                    up
FastEthernet0/1            unassigned      YES NVRAM  administratively down down
R1>exit
```

Python module `telnetlib` not only has basic methods for sending and receiving data but also has a few techniques (methods) that will watch and wait for a particular string to arrive from the remote system. The standard way to use it, see the Python script from telnetlib [docs](https://docs.python.org/3/library/telnetlib.html#telnet-example) and amend it, as per your requirement.

```py
import getpass
import telnetlib

# A variable for the IP address
HOST = "192.168.10.10" 
# A variable for the username
user = input("Enter your Username: ")
# Prompt the user for a password without echoing 
password = getpass.getpass()


# Variable 'HOST' to pass in to the object
tn = telnetlib.Telnet(HOST)
# read until found the `Username:`
tn.read_until(b"Username: ")
# Convert sending string to `ascii` encoding
tn.write(user.encode('ascii') + b"\n")
if password:
    tn.read_until(b"Password: ")
    tn.write(password.encode('ascii') + b"\n")
tn.write(b"sh ip int bri\n")  # Cisco command
tn.write(b"exit\n")

# Function 'read_all()' catch all return string
print(tn.read_all().decode('ascii'))
```

Output

```console
root@NetworkAutomation-1:~# python3 02_standard_script.py
Enter your Username: admin
Password:

R1>sh ip int bri
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            192.168.10.11   YES NVRAM  up                    up
FastEthernet0/1            unassigned      YES NVRAM  administratively down down
R1>exit
```

```{epigraph} **[getpass](https://docs.python.org/3/library/getpass.html)**
`getpass` module allows you to request a password without displaying input characters.
```

```{seealso}
See more code script at [GitHub](https://github.com/sydasif/network-automation/tree/master/telnet)
```
