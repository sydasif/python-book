# SSH

Using telnet in a lab environment for practice or in a fully isolated private network is recommended, but in a production or public network, telnet is vulnerable to cyber attack. To overcome this anomaly, network engineers use ssh. SSH is a network protocol that is widely used to access and manage a device remotely and a major protocol to access the network devices and servers over the internet.

## Paramiko Module

To automate networking devices via SSH, network engineer using Paramiko.

```{epigraph}
Paramiko is a pure-Python [1] (2.7, 3.4+) implementation of the SSHv2 protocol [2], providing both client and server functionality. It provides the foundation for the high-level SSH library Fabric, which is what we recommend you use for common client use-cases such as running remote shell commands or transferring files.

-- [Paramiko Docs](https://www.paramiko.org/)
```
