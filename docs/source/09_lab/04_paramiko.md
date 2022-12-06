# Paramiko Module

To automate networking devices via SSH, network engineer use Paramiko, as per module docs:

```{epigraph}
Paramiko is a pure-Python [1] (2.7, 3.4+) implementation of the SSHv2 protocol [2], providing both client and server functionality. It provides the foundation for the high-level SSH library Fabric, which is what we recommend you use for common client use-cases such as running remote shell commands or transferring files.

-- [Paramiko Docs](https://www.paramiko.org/)
```

To install paramiko simply use pip for installation.

```console
pip install paramiko
```

## Example of Paramiko

```py
import paramiko
import time

# Create an instance of the SSHClient class from Paramiko
client = paramiko.SSHClient()
# Sets the policy that the client should use regarding keys
client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
# The next few lines invoke a new interactive shell from the connection
client.connect('192.168.10.11',
                username='admin',
                password='cisco',
                look_for_keys=False,
                allow_agent=False
            )

ssh_client = client.invoke_shell()

# Send command to the remote device
ssh_client.send("sh ip int bri\n")
# Wait for the command to be finished
time.sleep(3)

'''if you did not clear out the received buffer? 
The output would just keep on filling up the buffer and would overwrite it.
For consistency of the output, we will retrieve the output from the 
buffer each time we execute a command.'''

output = ssh_client.recv(5000)
print(output.decode('ascii'))
# Close the remote connection
client.close()
```

```console
root@NetworkAutomation-1:~# python3 01_basic_paramiko.py

R1>sh ip int bri
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            192.168.10.11   YES NVRAM  up                    up
FastEthernet0/1            unassigned      YES NVRAM  administratively down down
R1>
```

### Example of for loop

In this python script, we use the `for` loop and `range()` functions to create a loopback interface on `R1`.

```py
import paramiko
import time

client = paramiko.SSHClient()
client.set_missing_host_key_policy(paramiko.AutoAddPolicy())

client.connect('192.168.10.11',
                username='admin',
                password='cisco',
                look_for_keys=False,
                allow_agent=False
            )

ssh_client = client.invoke_shell()
print('=====>>  Creating loop back <<=====')
ssh_client.send("enable\n")
ssh_client.send("cisco\n")
ssh_client.send("conf ter\n")

# For loop and range() function to create loop back interface
for num in range (0,2):
    ssh_client.send('int lo ' + str(num) + '\n')
    ssh_client.send('ip address 1.1.1.' + str(num) + ' 255.255.255.255\n')

time.sleep(1)
ssh_client.send('end\n')
ssh_client.send('show ip int brief\n')
time.sleep(3)
output = ssh_client.recv(65000)
print(output.decode('ascii'))
client.close()
print("### Done ###")
```

```console
root@NetworkAutomation-1:~# python3 02_for_loop_paramiko.py
=====>>  Creating loop back <<=====

R1>enable
Password:
R1#conf ter
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#int lo 0
R1(config-if)#ip address 1.1.1.0 255.255.255.255
R1(config-if)#int lo 1
R1(config-if)#ip address 1.1.1.1 255.255.255.255
R1(config-if)#end
R1#show ip int brief
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            192.168.10.11   YES NVRAM  up                    up
FastEthernet0/1            unassigned      YES NVRAM  administratively down down
Loopback0                  1.1.1.0         YES manual up                    up
Loopback1                  1.1.1.1         YES manual up                    up
R1#
### Done ###
```

### Connecting to multiple devices

In this python script, we use the `for` loop to connect multiple devices.

```py
import paramiko
import time

client = paramiko.SSHClient()
client.set_missing_host_key_policy(paramiko.AutoAddPolicy())

# For loop and range() function to connect multiple devices
for device in range(11,13):
    ip = "192.168.10." + str(device)
    print ('\n##### Connecting to the device ' + ip +' #####')

    client.connect(ip,
                  username='admin',
                   password='cisco',
                   look_for_keys=False,
                   allow_agent=False
               )

    ssh_client = client.invoke_shell()
    ssh_client.send("enable\n")
    ssh_client.send("cisco\n")
    ssh_client.send('show ip int brief\n')
    time.sleep(3)
    output = ssh_client.recv(65000)
    print(output.decode('ascii'))
    client.close()
print("### Done ###")
```

```console
root@NetworkAutomation-1:~# python3 03_for_loop_paramiko.py

##### Connecting to the device 192.168.10.11 #####

R1>enable
Password:
R1#show ip int brief
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            192.168.10.11   YES NVRAM  up                    up
FastEthernet0/1            unassigned      YES NVRAM  administratively down down
Loopback0                  1.1.1.0         YES manual up                    up
Loopback1                  1.1.1.1         YES manual up                    up
R1#

##### Connecting to the device 192.168.10.12 #####

R2>enable
Password:
R2#show ip int brief
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            unassigned      YES NVRAM  administratively down down
FastEthernet0/1            192.168.10.12   YES NVRAM  up                    up
Loopback0                  1.1.1.0         YES manual up                    up
Loopback1                  1.1.1.1         YES manual up                    up
R2#
### Done ###
```

In this python script, we use the `for` loop and `list` to connect to multiple devices.

```py
import paramiko
import time

username = 'admin'  # username
password = 'cisco'  # password

# IP list fo network device
devices =['192.168.10.11', '192.168.10.12']

# For loop and list to connect multiple devices
for device in devices:
    print ('\n #### Connecting to the device ' + device + ' ####\n' )

    client = paramiko.SSHClient()
    client.set_missing_host_key_policy(paramiko.AutoAddPolicy())

    client.connect(device,port=22,
                    username=username,
                    password=password,
                    look_for_keys=False,
                    allow_agent=False
                )

    ssh_client = client.invoke_shell()

    ssh_client.send('enable\n')
    ssh_client.send('cisco\n')
    ssh_client.send('config t\n')

    # For loop and range() function to create loop back interface
    for num in range (2,5):
        ssh_client.send('int lo ' + str(num) + '\n')
        ssh_client.send('ip address 1.1.1.' + str(num) + ' 255.255.255.255\n')

    time.sleep(1)
    ssh_client.send('do term length 0\n')
    ssh_client.send('do show ip int brief\n')
    time.sleep(3)
    output = ssh_client.recv(65000)
    print (output.decode('ascii'))

    client.close()
```

```console
root@NetworkAutomation-1:~# python3 04_list_paramiko.py

 #### Connecting to the device 192.168.10.11 ####


R1>enable
Password:
R1#config t
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#int lo 2
R1(config-if)#ip address 1.1.1.2 255.255.255.255
R1(config-if)#int lo 3
R1(config-if)#ip address 1.1.1.3 255.255.255.255
R1(config-if)#int lo 4
R1(config-if)#ip address 1.1.1.4 255.255.255.255
R1(config-if)#do term length 0
R1(config-if)#do show ip int brief
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            192.168.10.11   YES NVRAM  up                    up
FastEthernet0/1            unassigned      YES NVRAM  administratively down down
Loopback2                  1.1.1.2         YES manual up                    up
Loopback3                  1.1.1.3         YES manual up                    up
Loopback4                  1.1.1.4         YES manual up                    up

 #### Connecting to the device 192.168.10.12 ####


R2>enable
Password:
R2#config t
Enter configuration commands, one per line.  End with CNTL/Z.
R2(config)#int lo 2
R2(config-if)#ip address 1.1.1.2 255.255.255.255
R2(config-if)#int lo 3
R2(config-if)#ip address 1.1.1.3 255.255.255.255
R2(config-if)#int lo 4
R2(config-if)#ip address 1.1.1.4 255.255.255.255
R2(config-if)#do term length 0
R2(config-if)#do show ip int brief
Interface                  IP-Address      OK? Method Status                Protocol
FastEthernet0/0            unassigned      YES NVRAM  administratively down down
FastEthernet0/1            192.168.10.12   YES NVRAM  up                    up
Loopback2                  1.1.1.2         YES manual up                    up
Loopback3                  1.1.1.3         YES manual up                    up
Loopback4                  1.1.1.4         YES manual up                    up
```
