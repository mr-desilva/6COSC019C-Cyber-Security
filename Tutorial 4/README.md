- [1. Denial of Service Attacks](#1-denial-of-service-attacks)
  - [1.1 TCP flooding using hping3](#11-tcp-flooding-using-hping3)
  - [1.2 Smurf DoS attack using DDos Ripper](#12-smurf-dos-attack-using-ddos-ripper)
  - [1.3 MHDDos Attack Script With 51 Methods](#13-mhddos-attack-script-with-51-methods)
  - [1.4 Man in the Middle Attacks and Session Hijacking](#14-man-in-the-middle-attacks-and-session-hijacking)
  - [1.5 Setting up a spoofing attack with Ettercap - ARP Spoofing](#15-setting-up-a-spoofing-attack-with-ettercap---arp-spoofing)
  - [1.6 Modifying the data between the client and the server](#16-modifying-the-data-between-the-client-and-the-server)

----------


## 1. Denial of Service Attacks

### 1.1 TCP flooding using hping3

hping3 is application which can test the networking and systems at the network and transport layers. The testing approach is based on the three-phase communication which is SYN, SYN-ACK and ACK. TCP SYN flood happens when this handshake doesn't complete properly.

- type `top` in owasp vm to see the system usage, keep this open while performing the TCP SYN flood.
    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img1.png">

- go to kali vm and type `sudo hping3 192.168.56.102 --flood -S -p 445 ` .
  
    |Parameter|Definition|
    |:----|:----|
    |-S|default TCP mode|
    |-p 445|Specify the destination port which is 445|
    |-flood| specify a high omission rate to enable flooding.

    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img2.png">
----------


### 1.2 Smurf DoS attack using DDos Ripper

This attack consists of sending a series of ICMP echo requests with a spoofed source IP address to the network broadcast address. Less effective against the modern systems.

- Clone the repo from `git clone https://github.com/palahsu/DDoS-Ripper.git
`
- Navigate to project `cd DDoS-Ripper` and type `python3 DRipper.py`
- Next we will flood the OWASP vm with ICMP packet request using the following command. `python3 DRipper.py -s 192.168.56.104 -t 445` after entering open the windows VM and navigate to the server page. `http://192.168.56.102/`. You will notice a slow in the server but it does not crash.

    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img3.png">

----------


### 1.3 MHDDos Attack Script With 51 Methods

This script can be use to stress test websites using different methods.
- Clone the repository `git clone https://github.com/MHProDev/MHDDoS.git`
- Navigate to project `cd MHDDos` and install the requirements `pip install -r requirements.txt
`, after run the script `python3 start.py`.

    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img4.png">

- Run this command to flood the OWASP vm with TCP packets request from 1 thread for 3600 seconds. `python3 start.py tcp 192.168.56.104 1 3600
`. Next if you open the windows VM and navigate through server page there will be a delay when loading the pages.

    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img5.png">


----------

### 1.4 Man in the Middle Attacks and Session Hijacking
- A Man in the Middle (MITM) attack is the type of attack in which the attacker sets themselves in the middle of the communication line between two parties, usually a client and a server.
- This is done by breaking the original channel and then intercepting messages from one party and relaying them (sometimes with alterations) to the other.

----------


### 1.5 Setting up a spoofing attack with Ettercap - ARP Spoofing

Address Resolution Protocol (ARP) spoofing is maybe the most common MITM attack out there. It is based on the fact that the Address Resolution Protocol—the one that translates IP addresses to MAC addresses—does not verify the authenticity of the responses that a system receives.

- Open a root terminal and run `sudo ettercap -G`
  <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img6.png">
- Click on the right top tick and continue. Now click on the left side top icon with servers. Here you can see list of hosts in your private network. (If you can't see the hosts, click on the search icon)
  
  <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img7.png">
- Select the target host which is the OWASP vm (192.168.56.102) as target 1.
  
  <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img8.png">

- Click on the right side top icon with global and select MITM option ARP poisoning and click OK.

    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img9.png">

- Now move on to the windows VM and navigate to 'Damn Vulnerable Web Application' page and enter some credentials. After Clicking login check the ettercap terminal. You can see the username and the password from there.

    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img10.png">

    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img11.png">

----------
### 1.6 Modifying the data between the client and the server
Vulnerability : Command execution

`;ls` , `;pwd`

 <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img12.png">

1. Go to the Kali vm and type the command, Checking the port is open
    <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img13.png">
  
2. `; ls /bin/nc*`
   <img src="https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Tutorial%204/images/img14.png">

3. third
