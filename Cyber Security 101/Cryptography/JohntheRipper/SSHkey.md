
`id_rsa` is a **private SSH key file**

id_rsa
  ↓
ssh2john
  ↓
SSH hash representation
  ↓
John tries password guesses
  ↓
correct passphrase
  ↓
unlock/use id_rsa
  ↓
SSH authentication


`ssh2john` converts the `id_rsa` private key, which is used to log in to the SSH session, into a hash format

`python3 /opt/john/ssh2john.py`

`ssh2john [id_rsa private key file] > [output file`

![](../../assets/Pasted%20image%2020260814214623.png)


![](../../assets/Pasted%20image%2020260814214712.png)

