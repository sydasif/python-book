# Telnet and Secure Shell

In this section, I describe telnet and ssh to test our lab to connect to network devices.

- Telnet
- SSH

## Telnet

**Telnet**  is a type of network protocol that allows users on the Internet/local area networks to provide a bidirectional interactive text-oriented communication using a virtual terminal connection, to another device.

Telnet is easy to configure but not used often anymore since it is insecure, everything you do is sent in plaintext while SSH uses encryption. However, some older devices might only support telnet, so it’s good to know how to configure it.

### Telnet Server

Your router or switch will have a certain amount of VTY lines. These are virtual terminal lines. Let’s configure only the first five VTY lines:

```console
config ter
line vty 0 4
transport input all
login local
username admin password cisco
enable password cisco
end
wr
```

We now have an admin user with a password. Let’s test this:

```console
root@NetworkAutomation-1:~# telnet 192.168.10.11
Trying 192.168.10.11 ... Open

User Access Verification

Username: admin
Password:
R1>
```

As the above procedure configures `S-1` and `R-2`.

## Secure Shell

The Secure Shell Protocol (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network. Its most notable applications are remote login and command-line execution. SSH was designed on Unix-like operating systems, as a replacement for Telnet, using telnet in a lab environment for practice or in a fully isolated private network is recommended, but in a production or public network, telnet is vulnerable to cyber attack. To overcome this anomaly, network engineers use SSH.

```{epigraph}
SSH applications are based on a client-server architecture, connecting an SSH client instance with an SSH server.[2] SSH operates as a layered protocol suite comprising three principal hierarchical components: the transport layer provides server authentication, confidentiality, and integrity; the user authentication protocol validates the user to the server, and the connection protocol multiplexes the encrypted tunnel into multiple logical communication channels.

-- [Wikipedia](https://en.wikipedia.org/wiki/Secure_Shell)
```

## SSH Components

SSH is a protocol for creating an encrypted communication channel, protecting data passing between two networked hosts.

### SSH Server

An SSH server listens on the network for incoming SSH requests, authenticates those requests and provides a system command prompt.

### SSH Clients

Use an SSH client to connect your remote server to a network device, the most popular SSH client for windows systems is PuTTY.

## SSH Configuration

To authenticate an SSH connection, we need to set up RSA public/private key pair. We will configure SSH in lab {ref}`Lab Topology`, so that we can access it from any other device. NetworkAutomation-1 will be used as an SSH client.

The name of the RSA keypair will be the `hostname` and `domain` name of the router:

```console
config ter
ip domain-name cisco.local
crypto key generate rsa general-keys modulus 2048
end
wr
```

Now SSH to `R-1`:

```console
root@NetworkAutomation-1:~# ssh admin@192.168.10.11
The authenticity of host '192.168.10.11 (192.168.10.11)' can't be established.
RSA key fingerprint is SHA256:tayvAm8nMF0GH3JfMzdu4IVouM+nHzgJhD/WvZ5bFM8.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

Warning: Permanently added '192.168.10.11' (RSA) to the list of known hosts.
Password:

R1>en
Password:
R1#
```

As the above procedure configures `S-1` and `R-2` and accepts the fingerprint.
