
operates at the Application Layer, i.e., Layer 7 of the ISO OSI model.


- **First attempt:** DNS sends the query using **UDP port 53** because it's fast and has low overhead.
- **Fallback:** If UDP cannot handle the response or fails, DNS retries using **TCP port 53**


# A Record (Address Record)

**Purpose:** Maps a **hostname** to an **IPv4 address**.

```
example.com  ─────► 172.17.2.172
```

When you type:

```
https://example.com
```

Your computer asks the DNS server:

> "What is the IPv4 address of example.com?"

DNS replies:

```
172.17.2.172
```


# AAAA Record (Quad-A Record)

**Purpose:** Maps a hostname to an **IPv6 address**.

IPv6 addresses are much longer than IPv4.

Example:

```
example.com
      ↓
2001:db8:85a3::8a2e:370:7334
```


# CNAME Record (Canonical Name)

This one **doesn't point to an IP**.

Instead, it points **to another domain name**.

For example:

```
www.example.com
          ↓
example.com
```

DNS Record:

```
www.example.com   IN   CNAME   example.com
```


# MX Record (Mail Exchange)

MX records tell the Internet:

> **Which mail server receives emails for this domain?**

Suppose your email is:

```
alice@example.com
```

Someone sends you an email.

The sender's mail server asks DNS:

```
Who handles email for example.com?
```

DNS replies with the MX record.

Example:

```
example.com   IN   MX   mail.example.com
```

Now the sender knows:

```
Deliver the email to

mail.example.com
```


# Summary

|Record|Maps|Example|
|---|---|---|
|**A**|Domain → IPv4 address|`example.com → 172.17.2.172`|
|**AAAA**|Domain → IPv6 address|`example.com → 2001:db8::1`|
|**CNAME**|Domain → Another domain|`www.example.com → example.com`|
|**MX**|Domain → Mail server|`example.com → mail.example.com`|

