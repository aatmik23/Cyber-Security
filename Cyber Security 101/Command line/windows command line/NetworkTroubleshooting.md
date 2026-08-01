
`ipconfig`

![](../../assets/Pasted%20image%2020260801221911.png)

`ipconfig /all`

![](../../assets/Pasted%20image%2020260801222729.png)


`ping target_name`

`tracert example.com`

![](../../assets/Pasted%20image%2020260801223401.png)

Your PC
   |
Hop 1 - Home Router
   |
Hop 2 - ISP Router
   |
Hop 3 - ISP Core Router
   |
Hop 4 - Destination



`nslookup example.com`

It looks up a host or domain and returns its IP address.

```
nslookup example.com 1.1.1.1
```

Here:

- `example.com` = the domain you're looking up.
- `1.1.1.1` = the DNS server to ask.

`1.1.1.1` is a public DNS server provided by **Cloudflare**.

Flow:

```
Your PC
   │
   ▼
Cloudflare DNS (1.1.1.1)
   │
   ▼
example.com → 93.184.216.34
```




`netstat`

![](../../assets/Pasted%20image%2020260801225016.png)

current network connections and listening ports

- `-a` displays all established connections and listening ports
- `-b` shows the program associated with each listening port and established connection
- `-o` reveals the process ID (PID) associated with the connection
- `-n` uses a numerical form for addresses and port numbers

`netstat -abon`

![](../../assets/Pasted%20image%2020260801225252.png)

