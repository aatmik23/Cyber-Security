Like SSL, its predecessor, TLS is a cryptographic protocol operating at the OSI model’s transport layer. 


server administrator creates a Certificate Signing Request (CSR) and submits it to a Certificate Authority 

`https://google.com`

How do you know you are **really talking to Google** and not a hacker pretending to be Google?

TLS solves this by using **digital certificates**.`https://google.com`

How do you know you are **really talking to Google** and not a hacker pretending to be Google?

TLS solves this by using **digital certificates**.


a trusted organization to verify your identity.

That organization is called a **Certificate Authority (CA).**


Examples include:

- Let's Encrypt
- DigiCert
- Sectigo

Think of a CA like a government office issuing passports.

server administrator creates a **CSR**.

A CSR contains information like:

- Domain name
- Organization name
- Country
- Public key

Certificate

Owner:
example.com

Public Key:
ABC123XYZ

Signed by:
Let's Encrypt

![](../../assets/Pasted%20image%2020260803233834.png)