# Lab Setup with GNS3

GNS3 is used by hundreds of thousands of network engineers worldwide to emulate, configure, test and troubleshoot virtual and real networks. GNS3 allows you to run a small topology consisting of only a few devices on your laptop, to those that have many devices hosted on multiple servers or even hosted in the cloud.

```{figure} ../images/lab.png
---
width: 100%
name: topology
---
Lab 
```

GNS3 is open source, free software that you can download from <http://gns3.com>

## Basic settings for GNS3

We start with some basic knowledge about how to set up GNS3, download Cisco images and create new template in GNS3. There are a lot of tutorial videos from David Bombal on YouTube channel.

- [GNS3 installation](https://www.youtube.com/watch?v=Ibe3hgP8gCA)
- [GNS3 Install: VMware Workstation Pro](https://www.youtube.com/watch?v=A0DEnMi09LY)
- [Download Cisco IOS images and use in GNS3](https://www.youtube.com/watch?v=jhh2_PP9JLU&t=639s)

## Lab Setup

- Download the Network Automation appliance from GNS3 marketplace.
- Create the simple topology as the figure below in GSN3.

- **Network Automation docker container**

IP address configurations setup:

```console
# Static config for eth0
#auto eth0
#iface eth0 inet static
#       address 192.168.0.2
#       netmask 255.255.255.0
#       gateway 192.168.0.1
#       up echo nameserver 192.168.0.1 > /etc/resolv.conf

# DHCP config for eth0
auto eth0
iface eth0 inet dhcp

# Static config for eth1
auto eth1
iface eth1 inet static
        address 192.168.10.2
        netmask 255.255.255.0
#       gateway 192.168.10.1
#       up echo nameserver 192.168.10.1 > /etc/resolv.conf

# DHCP config for eth1
#auto eth1
#iface eth1 inet dhcp
```

- **Router Configuration**

Now configure the router `R1` in the same subnet as the container network address.

```console
config ter
hostname R1
int fa0/0
ip address 192.168.10.11 255.255.255.0
no shut
end
```

Configure the router `R2`

```console
config ter
hostname R2
int fa0/1
ip address 192.168.10.12 255.255.255.0
no shut
end
```

- **Switch Configuration**

Configure the IP address (192.168.10.10) on `VLAN1`, and check interface with `sh ip int brief`.

```console
config ter
int vlan 1
ip address 192.168.10.10 255.255.255.0
no shut
end
wr
```

```{seealso} **Download Network Automation docker container**
- [Part 1](https://www.youtube.com/watch?v=qsXDZTPnlro)
- [Part 2](https://www.youtube.com/watch?v=_iuz6x2vBSw&t=24s)
```
