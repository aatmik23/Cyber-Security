OSI (Open Systems Interconnection)

how communications should occur in a computer network.

framework for computer network communications.


- Physical Layer
- Data Link Layer
- Network Layer
- Transport Layer
- Session Layer
- Presentation Layer
- Application Layer

Please Do Not Throw Spinach Pizza Away


### Layer 1: Physical Layer

physical connection between devices;

wire
data transfer electrical, optical, or wireless signal.


### Layer 2: Data Link Layer

represents the protocol that enables data transfer between nodes on the same network segment. 

agreement dif system  --- how to communicate

layer 2 include Ethernet, i.e., 802.3, and WiFi, i.e., 802.11. Ethernet and WiFi addresses are six bytes

usually expressed in hexadecimal

two hexadecimal --- one byte

mac adress destination and source

![](../../assets/Pasted%20image%2020260803012543.png)


### Layer 3: Network Layer

layer 3, is concerned with sending data between different networks

the network layer handles logical addressing and routing

finding a path to transfer the network packets between the diverse networks.

Internet Protocol (IP), Internet Control Message Protocol (ICMP), and Virtual Private Network () protocols such as IPSec and SSL/ TLS

### Layer 4: Transport Layer

enables end-to-end communication between running applications on different hosts.

which can support various functions like flow control, segmentation, and error correction.


### Layer 5: Session Layer

establishing, maintaining, and synchronising communication between applications running on different hosts

intialize connection and negotiating the necessary parameters for the session.

session layer are Network FIle System (NFS) and Remote Procedure Call (RPC).

| Layer                   | Think of it as            | Job                                                                          |
| ----------------------- | ------------------------- | ---------------------------------------------------------------------------- |
| **Session Layer (5)**   | Managing the conversation | Starts, maintains, and ends the conversation                                 |
| **Transport Layer (4)** | Delivering each sentence  | Breaks data into pieces, delivers them reliably, and puts them back together |

### Layer6: Presentation Layer


delivered in a form the application layer can understand

data encoding, compression, and encryption


### Layer 7: Application Layer

provides network services directly to end-user applications.
browser would use the protocol to request a file, submit a form, or upload a file.

http ftp dns pop3 smtp imap

![](../../assets/Pasted%20image%2020260803014144.png)


