
![](../../assets/Pasted%20image%2020260803121736.png)

	32 bits 8 bit --- octet

`192.168.1.0` is the network address, while `192.168.1.255` is the broadcast address

Sending to the broadcast address targets all the hosts on the network.

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536
    inet 127.0.0.1/8

2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500
    inet 192.168.1.100/24

3: wlan0: <BROADCAST,MULTICAST> mtu 1500
    inet 192.168.1.105/24

### `lo`

```
lo
```

This is the **loopback interface**.

- Used for communication within the same computer.
- IP address:

```
127.0.0.1
```

---

### `eth0`

```
eth0
```

This is a wired Ethernet interface.

It has:

```
inet 192.168.1.100/24
```

which means:

- IP address: **192.168.1.100**
- Subnet mask: **/24** (equivalent to **255.255.255.0**)

---

### `wlan0`

```
wlan0
```

This is a Wi-Fi interface.

---

## Common Fields

### `inet`

```
inet 192.168.1.100/24
```

This is the **IPv4 address** assigned to the interface.


C 1918 defines the following three ranges of private IP addresses:

- `10.0.0.0` - `10.255.255.255` (`10/8`)
- `172.16.0.0` - `172.31.255.255` (`172.16/12`)
- `192.168.0.0` - `192.168.255.255` (`192.168/16`)


router must have a public IP address and must support Network Address Translation (NAT)

### Routing


a router forwards data packets to the proper network. Usually, a data packet passes through multiple routers before it reaches its final destination.

layer 3

packet to the best network (router) so the packet gets closer to its destination.