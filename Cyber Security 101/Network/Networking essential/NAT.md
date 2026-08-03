
NAT lies in using **one public IP address** to provide Internet access to **many private IP addresses**.

Before NAT:

```
Source IP = 192.168.1.10
Destination = Google
```

After NAT:

```
Source IP = 49.36.10.50   ← Router's public IP
Destination = Google
```

Google never sees:

```
192.168.1.10
```

It only sees:

```
49.36.10.50
```



# NAT Table

The router keeps a table.

Example:

|Internal Device|Public IP|Port|
|---|---|---|
|192.168.1.10|49.36.10.50|50001|
|192.168.1.11|49.36.10.50|50002|
|192.168.1.12|49.36.10.50|50003|