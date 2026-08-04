
Packet dissection is also known as protocol dissection, which investigates packet details by decoding available protocols and fields

Packets consist of 5 to 7 layers based on the OSI model.

![](../../assets/Pasted%20image%2020260804144226.png)

![](../../assets/Pasted%20image%2020260804144305.png)


seven distinct layers to the packet: `frame/packet`,`source [MAC]`,`source [IP]`,`protocol`,`protocol errors`, `application protocol`, and `application data`. Below we will go over the layers in more detail.

**The Frame (Layer 1):**

Frame (Wireshark metadata)
├── Frame Number: 27
├── Arrival Time
├── Frame Length
├── Captured Length
└── ...

The **Frame section in Wireshark** is **not the actual frame**. It is **information (metadata) about the captured frame**.

-------------------------------------------
**Ethernet II**  which is **Layer 2 (Data Link Layer)**.

Ethernet II
    Destination: Xerox_00:00:00 (00:00:00:00:00:00)
    Source: fe:ff:20:00:01:00
    Type: IPv4 (0x0800)


|   |   |
|---|---|
|0x0800|IPv4|

|   |   |
|---|---|
|0x86DD|IPv6|

|   |   |
|---|---|
|0x0806|ARP|

Destination MAC : AA:BB:CC:DD:EE:FF
Source MAC      : 11:22:33:44:55:66
Type            : IPv4 (0x0800)

Payload:
    ┌───────────────────────────────┐
    │ IPv4 Packet                   │
    │   ├── TCP Segment             │
    │   │      └── HTTP Data        │
    └───────────────────────────────┘


**payload** is the **actual data being carried** by the Ethernet frame.

Think of it as the **contents inside a package**.

------------------------------------

**Internet Protocol Version 4 (IPv4)** **Layer 3 (Network Layer)**.

	Source IP      = 192.168.1.15
Destination IP = 142.250.183.78

Flags
```
DF = 1
```

It means:

> **"Do NOT split this packet."**
- **DF = 0** → ✅ Fragmentation is **allowed**.
- **DF = 1** → ❌ Do **not** fragment the packet.
If the packet is too large for the network, the router **drops it** and sends an ICMP error back.

mf = 1 more packet are comming 
mf = 0 no more

| Field                  | Purpose                                                             |
| ---------------------- | ------------------------------------------------------------------- |
| **Version**            | IP version (usually IPv4 = 4)                                       |
| **Header Length**      | Size of the IP header                                               |
| **Total Length**       | Total size of the IP packet (header + data)                         |
| **Identification**     | Used if the packet is fragmented                                    |
| **Flags**              | Controls fragmentation (e.g., "Don't Fragment")                     |
| **Fragment Offset**    | Position of a fragment in the original packet                       |
| **TTL (Time To Live)** | Number of routers the packet can pass before being discarded        |
| **Protocol**           | Indicates what's inside the IP packet (TCP = 6, UDP = 17, ICMP = 1) |
| **Header Checksum**    | Detects errors in the IP header                                     |
| **Source IP**          | IP address of the sender                                            |
| **Destination IP**     | IP address of the receiver                                          |
| **Options**            | Optional settings (rarely used)                                     |


Protocol (Layer 4): 


**Protocol Errors:**This continuation of the 4th layer shows specific segments from TCP that needed to be reassembled.


This will show you details of the protocol used (TCP/UDP) and source and destination ports."

The Transport layer has **two main protocols**:

- **TCP (Protocol Number 6)**
- **UDP (Protocol Number 17)**



Transmission Control Protocol
    Source Port: 52345
    Destination Port: 443
    Sequence Number: 1001
    Acknowledgment Number: 5001
    Header Length: 20 bytes
    Flags: SYN, ACK
    Window Size: 64240
    Checksum: 0x1234


|Field|Meaning|
|---|---|
|**Source Port**|Which application sent the data|
|**Destination Port**|Which application should receive it|
|**Sequence Number**|Position of this data in the TCP stream|
|**Acknowledgment Number**|Confirms received data|
|**Flags**|SYN, ACK, FIN, RST, PSH, etc.|
|**Window Size**|How much data can be received before an acknowledgment is needed|
|**Checksum**|Detects errors in the TCP segment|


## Application Protocol (Layer 5)

| Protocol  | What it is used for                     |
| --------- | --------------------------------------- |
| **HTTP**  | Browsing websites                       |
| **HTTPS** | Secure websites                         |
| **DNS**   | Converting domain names to IP addresses |
| **FTP**   | File transfer                           |
| **SMTP**  | Sending emails                          |
| **POP3**  | Receiving emails                        |
| **IMAP**  | Managing emails on the server           |

Frame
│
├── Ethernet II
│     ├── Source MAC
│     └── Destination MAC
│
├── Internet Protocol Version 4
│     ├── Source IP
│     └── Destination IP
│
├── Transmission Control Protocol
│     ├── Source Port
│     ├── Destination Port
│     └── Flags
│
└── Hypertext Transfer Protocol
      ├── GET / HTTP/1.1
      ├── Host: tryhackme.com
      └── User-Agent: Firefox



An **ETag (Entity Tag)** is an **HTTP response header** that uniquely identifies a specific version of a resource (such as a web page, image, CSS file, or JavaScript file).

It helps browsers determine **whether a file has changed** so they don't download it again unnecessarily.

