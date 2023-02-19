### Initializing the VMs

1. Download the 3 VMs along with the virtual box.
2. Import the VMs using the Virtual box.

### Assigning IPs

1. OWASP Broken VM - This VM will be use as the vulnerable environment.
2. Windows 7 With IE8 - This VM will be use as the Victim.
3. KALI - This VM will be use as the attacker.

- Both OWASP and the Windows 7 IE8 VMs will be in a isolated network. KALI VM will be also set to the isolated virtual network while doing the lab activities. But in order to download certain packages and tools we will need to connect the KALI VM to the internet by simply changing the network adapter.

----------

### Host Only Adapter
Host-only networking is useful if you need to set up an isolated virtual network. In a host-only network, the virtual machine and the host virtual network adapter are connected to a private Ethernet network. The network is completely contained within the host system. 

### DHCP Server
Which allows to assign ip addresses for the connected nodes in a network to communicate with each other.

### Creating a private virtual network

1. Create a new virtual network from the Virtual box network manager.
<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%201/Images/img1.jpg" width="712" height="465">
2. Enable DHCP server, this will assign random IP address to the connected nodes (VMs) to the virtual network. Eg - range will be from 192.168.56.101 to 192.168.56.254
<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%201/Images/img2.jpg" width="712" height="465">
----------

### Adding VMs to the private virtual network

| **Network Adapter**      | **VM** |
| ----------- | ----------- |
| Host only adapter      | OWASP Broken       |
| Host only adapter   | Win 7 IE8        |
| Host only adapter (same private network group)   | KALI       |

### Getting IP addresses 

| **VM**     | **Command** |
| ----------- | ----------- |
| OWASP Broken       |    `ifconfig`   |
| Win 7 IE8   | `ifconfig`       |
| KALI    | `ifconfig` or `sudo ifconfig`       |

1. OWASP Broken<br>
<img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%201/Images/owaspip.jpg">
2. Wind 7 IE8
3. KALI
