
## UDP

User Datagram Protocol

simple connectionless protocol  

layer 4

there is no guarantee that the packet has been received successfully

A port number uses two octets.

2^16 = 65,536

Port **0** is **not used as a normal communication port**.

such as programming interfaces and testing

|Port|Service|
|--:|---|
|20, 21|FTP|
|22|SSH|
|23|Telnet|
|25|SMTP (Email)|
|53|DNS|
|80|HTTP|
|110|POP3|
|143|IMAP|
|443|HTTPS|



## TCP

Transmission Control Protocol

Being connection-oriented

- SYN Packet: The client initiates the connection by sending a SYN packet to the server. This packet contains the client’s randomly chosen initial sequence number.
- SYN-ACK Packet: The server responds to the SYN packet with a SYN-ACK packet, which adds the initial sequence number randomly chosen by the server.
- ACK Packet: The three-way handshake is completed as the client sends an ACK packet to acknowledge the reception of the SYN-ACK packet.
- 
![](../../assets/Pasted%20image%2020260803132110.png)