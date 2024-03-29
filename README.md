# 6COSC019C-Cyber-Security
## Lecture Short Note
Refer to my lecture short note from view only document [Mircrosoft One Note Cybersecurity Short Note.](https://1drv.ms/o/s!AimF5AtVXXGDnRIQx0P-mYJZAt2w?e=BZsyHu)
## Resources


| **Week Number**     | **Lecture** |  **Self Made MCQs** |
| ----------- | -----------  |-----------
| Week 1       |   [Information Systems Security Fundamentals](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%201%20-%20Information%20Systems%20Security%20Fundamentals/W1-Lec.pdf)   | -|
| Week 2   | [Network Security Fundamentals and Threats](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%202%20-%20Network%20Security%20Fundamentals%20and%20Threats/W2-Lec.pdf)      | [MCQ Paper](https://forms.gle/36edJBhYhoLS2GKF8)|
| Week 3    | [Cryptography and Cryptogrphic Tools](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%203%20-%20Cryptography%20and%20Cryptogrphic%20Tools/W3-Lec.pdf)      | [MCQ Paper](https://forms.gle/sBZAZ9jHpkzNsrcD9)|
| Week 4    | [AAA and Access Control](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%204%20-%20AAA%20and%20Access%20Control/W4-Lec.pdf)      | [MCQ Paper](https://forms.gle/7xYojaC2Hhj2eNBp9)|
| Week 5    | [Malicious software and adverserial behaviours](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%205%20-%20Malicious%20software%20and%20adverserial%20behaviours/W5-Lec.pdf)      | [MCQ Paper](https://forms.gle/ffMtMMLVieyzW1pt8)|
| Week 7    | [Software and Web application security](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%207%20-%20Software%20and%20Web%20application%20security/W7-Lec.pdf)      | [MCQ Paper](https://forms.gle/yfVK5eE6NNsSHw2C9)|
| Week 8    | [Defensive Technologies- Securing the Network and Services](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%208%20-%20Defensive%20Technologies-%20Securing%20the%20Network%20and%20Services/W8-Lec.pdf)      | [MCQ Paper](https://forms.gle/B7KWDgtzPZoLUiyz5)|
| Week 9    | [Defensive Technologies -(Intrusion Detection and Firewalls)](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%209%20-%20Defensive%20Technologies%20-(Intrusion%20Detection%20and%20Firewalls)/W9-Lec%20(1).pdf)      | [MCQ Paper]( https://forms.gle/cbjxsDYa6fWtaCEf6)|
| Week 10    | [Risk management principles, Plans and procedures](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%2010%20-%20Risk%20management%20principles%2C%20Plans%20and%20procedures/W10-Lec.pdf) | [-]()|
| Week 11    | [Security in various environments](https://github.com/mr-desilva/6COSC019C-Cyber-Security/blob/main/Lectures/Week%2011%20-%20Security%20in%20various%20environments/W11-Lec.pdf) | [-]()|

Sample MCQ papers are made by my self, not by the university.

Download VMs from the [UoW Link](https://download.ecs.westminster.ac.uk/VirtualMachines/) and import using the Virtual Box.





----------

### Save Terminal output as a log
Script is a unix utility command that records terminal session as a log file. Read the documentation from [here](https://man7.org/linux/man-pages/man1/script.1.html).

```
$ script output.txt
Script started, file is output.txt

# terminal session will be saved to the output.txt file.
# do your commands..........
#...................

$ exit
Script done, file is output.txt

# Now the session is recorded in the output.txt file.
# To open the file use the following command

$ cat output.txt
```



----------
### Static IPs
| **VM**     | **IP** |
| ----------- | ----------- |
| Kali       |   192.168.56.101  |
| OWASP | 192.168.56.102      |
| Win 7 IE8    | 192.168.56.103      |

----------



### Tutorial 1 - [Note ✅](https://github.com/mr-desilva/6COSC019C-Cyber-Security/tree/main/Tutorial%201)
- Setting up VMs
- Private virtual network
- Connecting VMs to the private virtual network
- Changing the network adapter


### Tutorial 2 - [Note ✅](https://github.com/mr-desilva/6COSC019C-Cyber-Security/tree/main/Tutorial%202)
- Basic Linux Commands
- File handling commands in linux
- User access controlling (Permission)
- Networking
- Linux package manager
### Tutorial 3 - [Note ✅](https://github.com/mr-desilva/6COSC019C-Cyber-Security/tree/main/Tutorial%203)
- OSINT tools
- TheHarvester
- SpiderFoot
- Recon-ng
- SIGIT – Simple Information Gathering Toolkit
- Information Gathering
### Tutorial 4 - [Note ✅](https://github.com/mr-desilva/6COSC019C-Cyber-Security/tree/main/Tutorial%204)
- TCP flooding using hping3
- Smurf DoS attack using DDos Ripper
- MHDDos Attack Script With 51 Methods
- Man in the Middle Attacks and Session Hijacking
- Setting up a spoofing attack with Ettercap - ARP Spoofing
