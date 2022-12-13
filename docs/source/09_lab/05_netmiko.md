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

## Getting Started with Netmiko

Import the `ConnectHandler()` class from the Netmiko library, creates an object, and establish an SSH connection to the remote device. The required arguments to pass in as dictionary to created object as below:

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

This script uses a dictionary and lists to SSH and configures multiple Cisco devices. It uses for loop to get each device from the dictionary.

```py
from netmiko import ConnectHandler

R1 = {
 'device_type': 'cisco_ios',
 'ip': '192.168.10.11',
 'username': 'admin',
 'password': 'cisco',
 'secret': 'cisco',
}

R2 = {
 'device_type': 'cisco_ios',
 'ip': '192.168.10.12',
 'username': 'admin',
 'password': 'cisco',
 'secret': 'cisco',
}

S1 = {
 'device_type': 'cisco_ios',
 'ip': '192.168.10.10',
 'username': 'admin',
 'password': 'cisco',
 'secret': 'cisco',
}

devices = [R1, R2, S1]

for device in devices:
    print()
    print (f"Connecting to the Host {device['ip']}")
    print()
    net_connect = ConnectHandler(**device)
    net_connect.enable()

    #  Create a list of configuration commands
    config_commands = ['username admin pri 15 password cisco']
    # Making Configuration Changes using send_config_set() method
    net_connect.send_config_set(config_commands)  # Pass that list to the send_config_set() method.
    # Save running-config to startup-config by executing the save_config() method.
    net_connect.save_config()

    output = net_connect.send_command('show running-config | section username')
    print(output)
```

```console
root@NetworkAutomation-1:~# python3 02_multi_device.py

Connecting to the Host 192.168.10.11


username admin privilege 15 password 0 cisco

Connecting to the Host 192.168.10.12


username admin privilege 15 password 0 cisco

Connecting to the Host 192.168.10.10


username admin privilege 15 password 0 cisco
```

### Configuration changes from a file

This script demonstrates, how to use the method `send_config_from_file()` in netmiko for device configuration. Using this you will be able to fetch config from external file and push to device.

````{margin}
Configuration file in the same dir

```console
$ cat config_file.cfg 
logging buffered 100000
no logging console
```
````

```py
from netmiko import ConnectHandler


S1 = {
 'device_type': 'cisco_ios',
 'ip': '192.168.10.10',
 'username': 'admin',
 'password': 'cisco',
 'secret': 'cisco',
}

net_connect = ConnectHandler(**S1)

file = "config_file.cfg"

with ConnectHandler(**S1) as net_connect:
    output = net_connect.send_config_from_file(file)
    output += net_connect.save_config()

print()
print(output)
print()
```

```console
root@NetworkAutomation-1:~# python3 03_config_file.py

configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
S1(config)#logging buffered 100000
S1(config)#no logging console
S1(config)#end
S1#write mem

Building configuration...
Compressed configuration from 3586 bytes to 1679 bytes[OK]
S1#
```

### Additional Examples

There are lots of additional examples [here](https://github.com/ktbyers/netmiko/blob/develop/EXAMPLES.md).
