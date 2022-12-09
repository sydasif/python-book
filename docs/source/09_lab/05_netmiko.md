# [Netmiko Module](https://pynet.twb-tech.com/blog/netmiko-python-library.html)

Netmiko is a multi-vendor library that simplifies SSH management to network devices, this library is based on the Paramiko SSH library. Netmiko supports a wide range of devices.

## Purpose

Netmiko simplifies SSH management to network devices. The purposes of this library are the following:

- Successfully establish an SSH connection to the device.
- Simplify the execution, retrieval, and formatting of show commands.
- Simplify the execution of configuration commands.
- Provide a (relatively) uniform API for interacting with devices.

To install netmiko simply use pip for installation.

```console
pip install netmiko
```

Netmiko has the following requirements (which pip will install for you)

- Paramiko >= 2.4.3
- scp >= 0.13.2
- pyserial
- textfsm

## Getting Started

Import the` ConnectHandler()` class from the Netmiko library, creates an object, and establish an SSH connection to the remote device. The required arguments to pass in as dictionary to created object as below:

- device_type
- hostname or IP
- username
- password

The next thing that to do is retrieve the show command output from the device, the script at this point is as below:

```py
from netmiko import ConnectHandler

# Create a dictionary 
R1 = {
 'device_type': 'cisco_ios',
 'ip': '192.168.10.11',
 'username': 'admin',
 'password': 'cisco',
 'secret': 'cisco',
}

'''calling the ConnectHandler Library [**R1] means telling python to consider 
the contents of the dictionary as key-value pairs instead of single elements.'''

net_connect = ConnectHandler(**R1)
net_connect.enable()  # device enable mode

# Sending a command into the switch --->
output = net_connect.send_command("show ip int brief")
print(output)
```

```console
root@NetworkAutomation-1:~# python3 01_basic_netmiko.py

Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            192.168.10.11   YES NVRAM  up                    up
FastEthernet0/1            unassigned      YES NVRAM  administratively down down
```
