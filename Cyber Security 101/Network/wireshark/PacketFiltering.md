
to filter and use the "right-click menu" or **"Analyse** **--> Apply as Filter"**

## Conversation Filter

focusing on IP addresses and port numbers. In that case, the "Conversation Filter"


## prepare as a filter

**Prepare as Filter** lets you **build a display filter without applying it immediately**.

This is useful when you're creating a complex filter step by step.

## Apply as coloum


**Apply as Column** in Wireshark adds the selected field as a **new column** in the packet list, so you can see that information for every packet without opening each one.


## follow stream

![](../../assets/Pasted%20image%2020260804183707.png)


Common protocol filters:

| Filter  | Shows                     |
| ------- | ------------------------- |
| `http`  | HTTP traffic              |
| `https` | HTTPS traffic (encrypted) |
| `dns`   | DNS queries/responses     |
| `arp`   | ARP packets               |
| `icmp`  | Ping packets              |
| `ftp`   | FTP traffic               |
| `smtp`  | Email (SMTP)              |
| `pop`   | POP3 email                |
| `imap`  | IMAP email                |
| `dhcp`  | DHCP traffic              |

Every protocol usually uses a port.

Examples:

|Port|Service|
|---|---|
|80|HTTP|
|443|HTTPS|
|21|FTP|
|22|SSH|
|25|SMTP|
|53|DNS|
|110|POP3|
|143|IMAP|

---

To find HTTP packets:

```
tcp.port == 80
```


# Filter by IP Address

Suppose you only care about:

```
192.168.1.10
```

Use:

```
ip.addr == 192.168.1.10
```



```
ip.src == 192.168.1.10
```

---

Only packets **going to** that IP:

```
ip.dst == 192.168.1.10
```


# Combining Filters

Find HTTP traffic from a specific IP:

```
http && ip.addr == 192.168.1.10
```

---

Find DNS from a specific IP:

```
dns && ip.src == 192.168.1.10
```

---

Find HTTP on port 80:

```
http && tcp.port == 80
```


