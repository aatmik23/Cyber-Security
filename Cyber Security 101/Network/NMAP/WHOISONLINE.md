
`192.168.0.1-10`

- `192.168.0.1/24`, and this would be equivalent to `192.168.0.0-255`
- Hostname: You can also specify your target by hostname, for example, `example.thm`

`-sn`  online host

```shell-session
:~# nmap -sn 192.168.66.0/24
```


When scanning a directly connected network, starts by sending ARP requests. When a device responds to the ARP request, labels it with “Host is up”.

- `192.168.11.1` is live and responded to the ICMP echo (ping) request.
- `192.168.11.2` seems down. Nmap sent two ICMP echo (ping) requests, two ICMP timestamp requests, two TCP packets to port 443 with the SYN flag set, and two TCP packets to port 80 with the ACK flag set. The target didn’t respond to any. We observe several ICMP destination unreachable packets from the `192.168.11.151` router.


discovers live hosts such as `-PS[portlist]`, `-PA[portlist]`, `-PU[portlist]` for TCP SYN, TCP ACK, and UDP discovery via the

`-sL`. This scan only lists the targets to scan without actually scanning them. For 
example, `nmap -sL 192.168.0.1/24` will list the 256 targets that will be scanned.



As we mentioned earlier, `-sn` aims to discover live hosts without attempting to discover the services running on them. This scan might be helpful if you want to discover the devices on a network without causing much noise.


