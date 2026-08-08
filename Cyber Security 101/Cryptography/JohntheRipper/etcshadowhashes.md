
The `/etc/shadow` file is the file on Linux machines where password hashes are stored.


date of last password change and password expiration informatio

you must have sufficient privileges to access the hashes.

## Unshadowing


 to crack `/etc/shadow` passwords, you must combine it with the `/etc/passwd` file for John to understand the data it’s being given

tool built into the John suite of tools called `unshadow`


`unshadow [path to passwd] [path to shadow]`

- `unshadow`: Invokes the unshadow tool
- `[path to passwd]`: The file that contains the copy of the `/etc/passwd` file you’ve taken from the lab machine
- `[path to shadow]`: The file that contains the copy of the `/etc/shadow` file you’ve taken from the lab machine

`unshadow local_passwd local_shadow > unshadowed.txt`


Contains the `/etc/passwd` line for the root user:

`root:x:0:0::/root:/bin/bash`

**FILE 2 - local_shadow**

Contains the `/etc/shadow` line for the root user: `root:$6$2nwjN454g.dv4HN/$m9Z/r2xVfweYVkrr.v5Ft8Ws3/YYksfNwq96UL1FX0OJjY1L6l.DS3KEVsZ9rOVLB/ldTeEL/OIhJZ4GMFMGA0:18576::::::`


`--format=sha512crypt`

`john --wordlist=/usr/share/wordlists/rockyou.txt --format=sha512crypt unshadowed.txt`

local_passwd  ─┐
               ├──→ unshadow → unshadowed.txt
local_shadow  ─┘




![](../../assets/Pasted%20image%2020260808213330.png)


![](../../assets/Pasted%20image%2020260808213312.png)