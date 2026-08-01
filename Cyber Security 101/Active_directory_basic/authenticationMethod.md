
all credentials are stored in the Domain Controllers.

Two protocols can be used for network authentication in windows domains:

- **Kerberos**:Used by any recent version of Windows. This is the default protocol in any recent domain.
- **NetNTLM:** Legacy authentication protocol kept for compatibility purposes.

most networks will have both protocols enabled.

Kerberos Authentication

use assigned a ticket

user sends their username and a timestamp encrypted using a key derived from their password to the **Key Distribution Center (KDC)

kdc send back a ticket granting ticket **tdt**
allow the user to request additional tickets to access specific services.

allows users to request service tickets without passing their credentials every time they want to connect to a service.

along tgt and session key given to user

tgt -- encrypted ---- **krbtgt** account's password hash

encrypted  TGT includes a copy of the Session Key as part of its contents,

![](../assets/Pasted%20image%2020260801201558.png)


user    ----- want to access service like website,database

user --     tgt ----> kdc          

user  <--------    TGS ticket granting servce
                 kdc

TGS  Tickets that allow connection only to the specific service

user will send their username and a timestamp encrypted using the Session Key

user ----    username timestamp   ------- to get TGS
              encrypted 
            (session key)
         along with TGT and
         **Service Principal Name**
         SPC  (service and service name)

![](../assets/Pasted%20image%2020260801202454.png)

service session key to access service

![](../assets/Pasted%20image%2020260801202607.png)


NetNTLM Authentication

The server generates a random number and sends it as a challenge to the client.

he client combines their password hash with the challenge (and other known data) to generate a response to the challenge and sends it back to the server for verification.



![](../assets/Pasted%20image%2020260801202939.png)





ntlm authentican part was confusing as no password and hash are being transfered

## Both sides already know the same secret

When you created your account:

```
Password = apple123
```

Windows stored the hash of the password.

Both the client and the server have access to the **same hash**.

```
Client                      Server
------                      ------
Hash = XYZ123               Hash = XYZ123
```

The hash is **never exchanged** during login.

---

## Step 1: Server sends a challenge

The server says:

```
Challenge = 25
```

and sends **25** to the client.

```
Client <---------------- Server
        Challenge = 25
```

---

## Step 2: Client calculates an answer

Imagine (this is **not** the real NTLM algorithm) the rule is:

```
Response = Hash + Challenge
```

Client computes:

```
XYZ123 + 25 = ABC999
```

and sends:

```
Response = ABC999
```

---

## Step 3: Server calculates the expected answer

The server already knows:

- Hash = XYZ123
- Challenge = 25

So it performs the **same calculation**:

```
XYZ123 + 25 = ABC999
```

Now it compares:

```
Client sent:      ABC999
Server computed:  ABC999
```

They match.

✅ Login successful.## Both sides already know the same secret

When you created your account:

```
Password = apple123
```

Windows stored the hash of the password.

Both the client and the server have access to the **same hash**.

```
Client                      Server
------                      ------
Hash = XYZ123               Hash = XYZ123
```

The hash is **never exchanged** during login.

---

## Step 1: Server sends a challenge

The server says:

```
Challenge = 25
```

and sends **25** to the client.

```
Client <---------------- Server
        Challenge = 25
```

---

## Step 2: Client calculates an answer

Imagine (this is **not** the real NTLM algorithm) the rule is:

```
Response = Hash + Challenge
```

Client computes:

```
XYZ123 + 25 = ABC999
```

and sends:

```
Response = ABC999
```

---

## Step 3: Server calculates the expected answer

The server already knows:

- Hash = XYZ123
- Challenge = 25

So it performs the **same calculation**:

```
XYZ123 + 25 = ABC999
```

Now it compares:

```
Client sent:      ABC999
Server computed:  ABC999
```

They match.

✅ Login successful.


