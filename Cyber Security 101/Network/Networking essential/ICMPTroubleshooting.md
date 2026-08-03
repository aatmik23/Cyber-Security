
Internet Control Message Protocol (ICMP) is mainly used for network diagnostics and error reporting.

`ping`: This command uses ICMP to test connectivity to a target system and measures the round-trip time (RTT)

`traceroute`: This command is called `traceroute` on Linux and UNIX-like systems and `tracert` on MS Windows systems. It uses ICMP to discover the route from your host to the target.

 PING send an ICMP Echo Request (ICMP Type `8`).
![](../../assets/Pasted%20image%2020260803165519.png)

computer on the receiving end responds with an ICMP Echo Reply (ICMP Type `0`).

![](../../assets/Pasted%20image%2020260803165547.png)


`-c 4` to tell the `ping` command to stop after sending four packets.

```shell-session
user@TryHackMe$ ping 192.168.11.1 -c 4
PING 192.168.11.1 (192.168.11.1) 56(84) bytes of data.
64 bytes from 192.168.11.1: icmp_seq=1 ttl=63 time=11.2 ms
64 bytes from 192.168.11.1: icmp_seq=2 ttl=63 time=3.81 ms
64 bytes from 192.168.11.1: icmp_seq=3 ttl=63 time=3.99 ms
64 bytes from 192.168.11.1: icmp_seq=4 ttl=63 time=23.4 ms

--- 192.168.11.1 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3003ms
rtt min/avg/max/mdev = 3.805/10.596/23.366/7.956 ms
```


moreover, it calculates the minimum, average, maximum, and standard deviation (mdev) of the round-trip time (RTT).


### Traceroute

Internet protocol has a field called Time-to-Live () that indicates the maximum number of routers a packet can travel through before it is dropped.

When the ttl reaches zero, the router drops the packet and sends an ICMP Time Exceeded message (ICMP Type `11`).

ttl default value 64 we use it so we dont get stuck in loop router 4 -----> <------ router b

**ICMP Time Exceeded** message