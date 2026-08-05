
process that listing to tcp and udp request

web servers, which usually listen on TCP ports 80 and 443, and DNS servers, which typically listen on UDP (and TCP) port 53.

telnet connect on any devie tcp port open firewall not block

	`telnet` command is simply a **TCP client**.

connect scan can be triggered using `-sT`

![](../../assets/Pasted%20image%2020260805141726.png)

![](../../assets/Pasted%20image%2020260805140619.png)

#### SYN Scan (Stealth)

send tcp syn packet

fewer logs as the connection is never established,

can select the SYN scan using the `-sS` flag.

![](../../assets/Pasted%20image%2020260805140814.png)



### Scanning UDP Ports


DNS, DHCP, NTP (Network Time Protocol), SNMP (Simple Network Management Protocol), and VoIP (Voice over IP)

option `-sU` to scan for services.

Scanner                  Server
UDP Packet -------------->
     <------------------- ICMP Destination Unreachable
                          (Port Unreachable)


Nmap
  │
  ├── Sends UDP packet to port 53
  │
  ├── If closed:
  │      ← ICMP Port Unreachable
  │
  ├── If open:
  │      ← UDP response (sometimes)
  │
  └── If no response:
         open|filtered


### Limiting the Target Ports

`-F` is for Fast mode, which scans the 100 most common ports

`-p[range]`        `-p10-1024` scans from port 10 to port 1024, while `-p-25` will scan all the ports between 1 and 25


`-p-`  1-65535



| Option      | Explanation                                                   |
| ----------- | ------------------------------------------------------------- |
| `-sT`       | TCP connect scan – complete three-way handshake               |
| `-sS`       | SYN – only first step of the three-way handshake              |
| `-sU`       | UDP scan                                                      |
| `-F`        | Fast mode – scans the 100 most common ports                   |
| `-p[range]` | Specifies a range of port numbers – `-p-` scans all the ports |




