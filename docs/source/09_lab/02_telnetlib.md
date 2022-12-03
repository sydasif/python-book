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
Deprecated since version 3.11, will be removed in version 3.13
```

Copy the python script from telnetlib [docs](https://docs.python.org/3/library/telnetlib.html#telnet-example) to your PC and amend it, as per your requirement.

```py
import getpass
import telnetlib

HOST = "192.168.10.10"  # A variable for storing the IP address
user = input("Enter your Username: ")  # A variable for storing username
password = getpass.getpass()  # To get the password from the user


# HOST variable pass in to the class object
tn = telnetlib.Telnet(HOST)

tn.read_until(b"Username: ")  # read until found the `Username:`

# Convert sending string to `ascii` encoding
tn.write(user.encode('ascii') + b"\n")
if password:
    tn.read_until(b"Password: ")
    tn.write(password.encode('ascii') + b"\n")

# Send Cisco command    
tn.write(b"sh ip int bri\n")
tn.write(b"exit\n")

# read_all() function will show the output after decoding
print(tn.read_all().decode('ascii'))
```

Output

```console
root@NetworkAutomation-1:~# python3 01_telnet.py
Enter your Username: admin
Password:

R1>sh ip int bri
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            192.168.10.11   YES NVRAM  up                    up
FastEthernet0/1            unassigned      YES NVRAM  administratively down down
R1>exit

root@NetworkAutomation-1:~#
```

