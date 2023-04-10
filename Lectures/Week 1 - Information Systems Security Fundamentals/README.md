# Information Systems Security Fundamentals

## Passive attacks and Active Attacks

### Passive Attacks
- Attempts to learn or make use of information from the system but does not affect the system resources.
- Eavesdropping on, or monitoring of transmissions.
- Goal is to obtain information.
- Example = Release of message contents, analysis
  
### Active Attacks
- Attempts to alter system resources or affect their operation.
- Data modification or create a false stream.
- Examples = Replay, masquerade, modification of messages, denial of service
----------


## Penetration Testing 
To test the security of systems and architectures from the pov of an attacker.

Whitebox testing - Full information about the target is shared with the testers. This type of testing confirms the efficacy of internal vulnerability assessment and management controls by identifying the existence of known software vulnerabilities and common misconfigurations in an organisation's systems.

Blackbox testing - No information is shared with the testers about the internals of the target. This type of testing is performed from and external perspective and is aimed at identifying ways to access and organization's internal IT assets.

### The process of pen test

1. Data gathering
	- Gathering data from the target using OSINT tools. These data includes identifying network layouts, domains, servers etc.
	- Reconnaissance stage is for gather additional information that may have been overlooked, unknown or not provided.
2. Enumeration
	- Using the gathered data the attacker establishes and active connection to the target host. Mainly to search for attacks and threats to the target system.
	- Used to collect usernames, hostnames, IP, passwords and configurations etc.
3. Data Exfiltration
   -  Once connected to the target system, testers use tools and techniques to extract data from the network.