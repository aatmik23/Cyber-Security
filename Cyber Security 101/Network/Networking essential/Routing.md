
routing algorithms are beyond the scope of this room

**OSPF (Open Shortest Path First)**: 
OSPF is smarter.

Instead of counting routers, it looks at the **cost** of each path.

Cost depends on things like:

- Bandwidth
- Link speed

Example:

```
      Slow Link
A ------------ B
 \            /
  \          /
   \        /
    C------
     Fast Link
```

Even if the bottom path has more routers, OSPF may choose it because it's **faster**.

**Easy memory:**

> **OSPF = Chooses the fastest path, not just the shortest.**


**EIGRP (Enhanced Interior Gateway Routing Protocol)**

cisco proprietary routing protocol
# The smart decision maker"

EIGRP looks at many things:

- Bandwidth ✅
- Delay ✅
- Reliability ✅
- Load ✅

Imagine choosing a road.

Instead of asking only:

> "Is it short?"

EIGRP asks:

- Is it fast?
- Is there traffic?
- Is it reliable?

Then it chooses the best one.

**Easy memory:**

> **EIGRP = Smart router that checks many factors.**es.

**BGP (Border Gateway Protocol)**:

# The Internet's GPS"

BGP is completely different.

The others (RIP, OSPF, EIGRP) are mostly used **inside one organization**.

Example:

```
Google Network
```

or

```
Amazon Network
```

BGP is used **between organizations**.

Example:

```
Google
    │
    │ BGP
    ▼
Airtel
    │
    │ BGP
    ▼
Jio
    │
    │ BGP
    ▼
Cloudflare
```

The Internet is made of thousands of networks called **Autonomous Systems (AS)**.

BGP tells them:

> "To reach Google's network, send traffic this way."

Without BGP, the Internet wouldn't know how to send traffic between different companies.

**Easy memory:**

> **BGP = Internet routing protocol.**

**RIP (Routing Information Protocol)**:

simple routing protocol often used in small networks.

RIP share information about the networks they can reach and the number of hops (routers) required to get there.

router builds a routing table based on this information, choosing the routes with the fewest hops to reach each destination.

# Summary

| Protocol  | Easy Meaning                                                    | Used Where                   |
| --------- | --------------------------------------------------------------- | ---------------------------- |
| **RIP**   | Counts hops (routers)                                           | Small networks               |
| **OSPF**  | Chooses the lowest-cost (usually fastest) path                  | Large enterprise networks    |
| **EIGRP** | Uses multiple factors (bandwidth, delay, etc.) to choose a path | Primarily Cisco environments |
| **BGP**   | Routes traffic between different organizations on the Internet  | The Internet                 |