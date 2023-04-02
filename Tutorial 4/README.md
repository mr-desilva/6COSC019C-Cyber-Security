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
