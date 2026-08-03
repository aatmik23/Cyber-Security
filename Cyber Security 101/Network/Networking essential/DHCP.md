network we need to configure

- IP address along with subnet mask
- Router (or gateway)
- DNS server

Dynamic Host Configuration Protocol

is an application-level protocol that relies on UDP

the server listens on UDP port 67,

the client sends from UDP port 68


![](../../assets/Pasted%20image%2020260803162405.png)


![](../../assets/Pasted%20image%2020260803162453.png)

The server responds with a DHCPACK message to confirm that the offered IP address is now assigned to this client.

![](../../assets/Pasted%20image%2020260803162612.png)


```shell-session
user@TryHackMe$ tshark -r DHCP-G5000.pcap -n
    1   0.000000      0.0.0.0 → 255.255.255.255 DHCP 342 DHCP Discover - Transaction ID 0xfb92d53f
    2   0.013904 192.168.66.1 → 192.168.66.133 DHCP 376 DHCP Offer    - Transaction ID 0xfb92d53f
    3   4.115318      0.0.0.0 → 255.255.255.255 DHCP 342 DHCP Request  - Transaction ID 0xfb92d53f
    4   4.228117 192.168.66.1 → 192.168.66.133 DHCP 376 DHCP ACK      - Transaction ID 0xfb92d53f
```


, in the first and third packets, the client sends to the broadcast MAC address