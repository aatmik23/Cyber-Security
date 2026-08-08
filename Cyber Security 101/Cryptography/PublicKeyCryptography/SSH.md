
ssh verify the client digital finger print

ED25519 algo for digital signature generation and verify

we need to verify and authentecate 

ssh keys are rsa keys you can choose which algorithem to generate and passpharse 


ssh-keygen programs are usually used to generait key pair


server give cryptography operation and you solve it with pvt key and share result with server and it verify it

~/.ssh/id_rsa --> pvt
~/.ssh/id_rsa.pub


passphrase

private key --> encrypted with passpharse --> protected private key


prove you are authentic user

you have private key --> server have your public key --> server send challlenge --> solve it with pvt create cyptography proof 


new devic e--> generate new key pair 

pvt key stay on device and public key stay on the server

new device can ssh

```shell-session
man ssh-keygen
[...]
-t dsa | ecdsa | ecdsa-sk | ed25519 | ed25519-sk | rsa
Specifies the type of key to create. The possible values are “dsa”, “ecdsa”, “ecdsa-sk”, “ed25519”, “ed25519-sk”, or “rsa”.
[...]
```

- **DSA (Digital Signature Algorithm)** is a public-key cryptography algorithm specifically designed for digital signatures.
- **ECDSA (Elliptic Curve Digital Signature Algorithm)** is a variant of DSA that uses elliptic curve cryptography to provide smaller key sizes for equivalent security.
- **ECDSA-SK (ECDSA with Security Key)** is an extension of ECDSA. It incorporates hardware-based security keys for enhanced private key protection.
- **Ed25519** is a public-key signature system using EdDSA (Edwards-curve Digital Signature Algorithm) with Curve25519.
- **Ed25519-SK (Ed25519 with Security Key)** is a variant of Ed25519. Similar to ECDSA-SK, it uses a hardware-based security key for improved private key protection.



```shell-session
root@TryHackMe# ssh-keygen -t ed25519
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/strategos/.ssh/id_ed25519): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/strategos/.ssh/id_ed25519
Your public key has been saved in /home/strategos/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:4S4DQvRfp52UuNwg++ strategos@g5000
The key's random art image is:
+--[ED25519 256]--+
|  .       +XXB.  |
| . .     . oBBo  |
|  . . . = + o=o  |
| .   . * X .o.E  |
|  . . o S +  o . |
|   . . o .. + o  |
|      o +. + o   |
|       +. .      |
|        ..       |
+----[SHA256]-----+
```


Using tools like John the Ripper, you can attack an encrypted SSH key to attempt to find the passphrase, highlighting the importance of using a complex passphrase and keeping your private key private.

You **keep the private key on your own computer**.

You copy only the public key to the remote machine:

```
ssh-copy-id user@remote-machine
```

So:

```
YOUR MACHINE                  REMOTE MACHINE
─────────────                 ──────────────
private key 🔒                authorized_keys
     │                              ↑
     │                              │
     └────── public key ────────────┘
```

The private key **never needs to be placed on the remote machine**.


```
chmod 600 privateKeyFile
```

`600` means:

```
Owner:  read + write  ✅
Group:  nothing       ❌
Others: nothing       ❌
```


### How do you use a specific private key?

For example:

```
ssh -i privateKeyFile user@host
```



`authorized_keys`


authorized_keys
        │
        ├── Bob's public key
        ├── Alice's public key
        └── Admin's public key