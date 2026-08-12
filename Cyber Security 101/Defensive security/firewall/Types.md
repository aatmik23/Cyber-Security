

### Stateless Firewall

A **stateless firewall** checks each packet **independently** using predefined rules, mainly at **Layer 3 and Layer 4**.

- Does **not remember previous connections**
    
- Faster because it has no connection tracking
    
- Cannot make decisions based on previous packets
    

**Example:** If it blocks one packet from an IP, it doesn't remember that decision for future packets.

### Stateful Firewall

A **stateful firewall** tracks active connections and stores their information in a **state table**.

- Mainly operates at **Layer 3 and Layer 4**
    
- Remembers previous packets/connections
    
- Allows or blocks future packets based on connection history
    
- More secure but uses more resources than stateless firewalls
    

**Example:** If a connection is allowed, future packets belonging to that connection can be automatically allowed because the firewall **remembers the connection**.


A **proxy firewall** acts as an **intermediary between the client and the destination server**. The client does not communicate directly with the server.

```
Client → Proxy Firewall → Internet/Server
          ↓
       Inspects traffic
```

### How it works

Suppose you visit a website:

```
You → Proxy Firewall → Website
```

- Works mainly at **Layer 7 (Application Layer)**
- Acts as an **intermediary**
- Can inspect application-level data such as HTTP requests
- Can block specific websites, URLs, or content
- Can hide the client's IP address from the destination
- Provides more detailed inspection than basic packet filtering

![](../../assets/Pasted%20image%2020260810215402.png)