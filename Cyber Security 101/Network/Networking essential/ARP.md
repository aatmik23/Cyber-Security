Host A
   │
   │ ARP Request
   │ Destination MAC = ff:ff:ff:ff:ff:ff
   ▼
Everyone on the LAN receives it
   │
   ├── Host C: Not my IP ❌
   ├── Host D: Not my IP ❌
   └── Host B: That's my IP! ✅
               │
               ▼
         ARP Reply
         "My MAC is BB:BB:BB:BB:BB:BB"

Now Host A knows Host B's MAC and can send normal Ethernet frames directly to it.


ethernet need mac address to comunicate


```shell-session
user@TryHackMe$ tcpdump -r arp.pcapng -n -v
17:23:44.506615 ARP, Ethernet (len 6), IPv4 (len 4), Request who-has 192.168.66.1 tell 192.168.66.89, length 28
17:23:44.510182 ARP, Ethernet (len 6), IPv4 (len 4), Reply 192.168.66.1 is-at 44:df:65:d8:fe:6c, length 28
```

![](../../assets/Pasted%20image%2020260803164348.png)


`ff:ff:ff:ff:ff:ff` is a **special MAC address** called the **broadcast MAC address**.

