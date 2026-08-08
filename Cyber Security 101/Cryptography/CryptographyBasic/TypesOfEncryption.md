


two main categories of encryption are **symmetric** and **asymmetric**.


## Symmetric Encryption

![](../../assets/Pasted%20image%2020260806211118.png)


use same key

example

DES Data Encryption Standard)
3DES 
AES Advanced Encryption Standard).


des     56-bit key.   24hr break shift

3des   168 bits

ades  128, 192, or 256 bits.


The key is sent through an already secure channel, such as:

- A trusted courier
- An encrypted USB drive
- A secure VPN
- A protected internal network



## Asymmetric 

	**asymmetric cryptography** encrypts the data using the public key; hence, it is also called **public key cryptography**.

![](../../assets/Pasted%20image%2020260806212915.png)


	example RSA diffie hellman  ecc Elliptic Curve cryptography 


encrypted with the public key can be decrypted with the private key.


slow  

2048-bit is the recommended minimum key size

Alice                          Bob
------                         ------
Public Key 🔓 ---------------> Public Key 🔓
Private Key 🔒                 Private Key 🔒

Alice → Bob:
Encrypt with Bob's Public Key
Bob decrypts with Bob's Private Key

Bob → Alice:
Encrypt with Alice's Public Key
Alice decrypts with Alice's Private Key
