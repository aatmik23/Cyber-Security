encapsulation refers to the process of every layer adding a header (and sometimes a trailer) to the received unit of data and sending the “encapsulated” unit to the layer below.

**Application data**:
user inputs the data they want to send into the application
instant message and hit the send button.

application protocol used,

**Transport protocol segment or datagram**: 

adds the proper header information and creates the tcp or udp
This segment is sent to the layer below it, the network layer.

**Network packet**:

adds an IP header to the received tcp segment or udp datagram
IP **packet** is sent to the layer below it, the data link layer.

 **Data link frame**:
or WiFi receives the IP packet and adds the proper header and trailer, creating a **frame**.

![](../../assets/Pasted%20image%2020260803132950.png)



