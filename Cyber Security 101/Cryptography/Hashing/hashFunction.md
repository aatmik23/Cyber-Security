A hash function takes some input data of any size and creates a summary or **digest** of that data. The output has a fixed size.


their MD5 (Message-Digest Algorithm 5) hashes, their SHA1 (Secure Hash Algorithm 1) hashes, or their SHA-256 (Secure Hash Algorithm 256) hashes,


Common encodings are base64 or hexadecimal.

`md5sum`, `sha1sum`, `sha256sum`, and `sha512sum` produce their outputs in hexadecimal format.

 hexadecimal format prints each raw byte as two hexadecimal digits.



![](../../assets/Pasted%20image%2020260807223737.png)


### Hash Collision

two different inputs give the same output.

inputs is practically unlimited and the number of possible outputs is limited, this leads to a pigeonhole effect.

The **pigeonhole effect** states that the number of items (_pigeons_) is more than the number of containers (_pigeonholes_); some containers must hold more than one item


MD5 and SHA1 have been attacked and are now considered insecure due to the ability to engineer hash collisions.


![](../../assets/Pasted%20image%2020260807224705.png)

possible values
