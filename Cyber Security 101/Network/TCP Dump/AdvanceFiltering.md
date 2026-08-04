
- `greater LENGTH`: Filters packets that have a length greater than or equal to the specified length
- `less LENGTH`: Filters packets that have a length less than or equal to the specified length

`pcap-filter`

`&`, `|`, and `!`.

### Header Bytes

`proto[expr:size]`,

`proto` refers to the protocol. For example, `arp`, `ether`, `icmp`, `ip`, `ip6`, `tcp`, and `udp` refer to ARP, Ethernet, ICMP, IPv4, IPv6, TCP, and respectively.

`expr` indicates the byte offset, where `0` refers to the first byte

`size` indicates the number of bytes that interest us, which can be one, two, or four. It is optional and is one by default

## `ether[0] & 1 != 0`

### `ether[0]`

- `ether` = Ethernet header.
- `[0]` = the **first byte** of the Ethernet header.

The Ethernet header begins with the **destination MAC address**, so `ether[0]` is the **first byte of the destination MAC address**.

Example:

```
Destination MAC:
01:00:5e:00:00:fb

First byte = 01
Binary      = 00000001
```

---

### `& 1`

`1` in binary is:

```
00000001
```

The `&` (bitwise AND) compares each bit.

Example:

```
00000001   (first byte)
00000001   (& 1)
--------
00000001
```

Result = `1`

Since:

```
1 != 0
```

the filter matches.


## `ip[0] & 0xf != 5`

### `ip[0]`

The first byte of an IPv4 header contains **two fields**:

```
0100 0101
^^^^ ^^^^
 |      |
 |      +---- IHL (Internet Header Length)
 |
 +----------- Version
```

For a normal IPv4 packet:

```
01000101
```

- `0100` = Version 4
- `0101` = IHL = 5

---

### `0xf`

Hexadecimal:

```
0xf = 15 decimal
```

Binary:

```
00001111
```

This is called a **mask**.

It keeps only the **last four bits**.

---

### Example

Normal packet:

```
01000101
00001111
--------
00000101
```

Result:

```
5
```

Then:

```
5 != 5
```

False.

So the packet is ignored.


You can use `tcp[tcpflags]` to refer to the flags field. The following flags are available to compare with:

- `tcp-syn` SYN (Synchronize)
- `tcp-ack` ACK (Acknowledge)
- `tcp-fin` FIN (Finish)
- `tcp-rst` RST (Reset)
- `tcp-push` Push

- `tcpdump "tcp[tcpflags] == tcp-syn"` to capture packets with **only** the SYN (Synchronize) flag set, while all the other flags are unset.
- `tcpdump "tcp[tcpflags] & tcp-syn != 0"` to capture packets with **at least** the SYN (Synchronize) flag set.
- `tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"` to capture packets with **at least** the SYN (Synchronize) **or** ACK (Acknowledge) flags set.


![](../../assets/Pasted%20image%2020260805003403.png)
