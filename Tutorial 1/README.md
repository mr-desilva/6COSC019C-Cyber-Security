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
| Win 7 IE8   | `ipconfig`       |
| KALI    | `ifconfig` or `sudo ifconfig`       |

1. [OWASP Broken](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%201/Images/owaspip.jpg)<br>
```
root@owaspbwa : `# ifconfig
eth0    Link encap:Ethernet HWaddr 08:00:27:bd;8d;b3
        inet addr:192.168.56.103 Bcast:192.168.56.255 Mask:255.255.255.0
        inet6 addr: fe80::a00:27ff:febd:8db3/64 Scope:Link
        UP BROADCAST RUNNING MULTICAST MTU:1500 Metric:1
        RX packets:668 errors:0 dropped:0 overruns:0 frame:0
        TX packets:215 errors:0 dropped:0 overruns:0 carrier:0
        collisions:0 txqueuelen:1000
        RX bytes:85749 (85.7KB) TX bytes:40407 (40.4KB)
        Interrupt:9 Base address:0xd020
```

2. [Wind 7 IE8](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%201/Images/win7ip.jpg)<br>

```
PS C:\Windows\system32> ipconfig
Windows IP Configuration
Ethernet adapter Local Area Connection 2:

   Connection-specific DNS Suffix  . :
   Link-local IPv6 Address . . . . . : fe80::6950:8316:ebca:5aeb%15
   IPv4 Address. . . . . . . . . . . : 192.168.56.104
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . :

Tunnel adapter isatap.{53152A2F-39F7-458E-BD58-24D17099256A}:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :
```

3. [KALI](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%201/Images/kaliip.jpg")<br>
```
kali@kali:~$ sudo ifconfig
[sudo] password for kali: 
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.0.2.15  netmask 255.255.255.0  broadcast 10.0.2.255
        inet6 fe80::a00:27ff:fe5c:6526  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:5c:65:26  txqueuelen 1000  (Ethernet)
        RX packets 4  bytes 930 (930.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 27  bytes 2313 (2.2 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 12  bytes 556 (556.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 12  bytes 556 (556.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```


----------
### Pinging Connected Devices In The Same Private Virtual Network
Since all the VMs are connected to a private virtual network it should be possible to ping each machine from the VMs using the ip addresses.

Type `ping <ip_address>` in the terminal to ping a VM. Will result something similar like this.

```
kali@kali:~$ ping 192.168.56.104
PING 192.168.56.104 (192.168.56.104) 56(84) bytes of data.
64 bytes from 192.168.56.104: icmp_seq=1 ttl=127 time=1.19 ms
64 bytes from 192.168.56.104: icmp_seq=2 ttl=127 time=0.936 ms
64 bytes from 192.168.56.104: icmp_seq=3 ttl=127 time=0.936 ms
64 bytes from 192.168.56.104: icmp_seq=4 ttl=127 time=0.974 ms
64 bytes from 192.168.56.104: icmp_seq=5 ttl=127 time=1.08 ms
^C
--- 192.168.56.104 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4007ms
rtt min/avg/max/mdev = 0.936/1.021/1.186/0.096 ms

```
----------

### Connecting KALI VM to the Internet
All three VMs are now in a private network which is isolated from the internet connectivity. Sometimes we need to connect the Kali vm to the internet for package installation. Therefore we can connect the VM to the internet using these methods.

1. By changing the network mode to NAT from the settings --> then disconnect the network from the VM settings and turn it on.
2. By using command line,
- Stop the running network interface by using this command `sudo ifconfig eth0 down`
- Turn on the interface again using this command `sudo ifconfig eth0 up`


