
pass salt can be decrypt 

	crack hashes by hashing many different input 

hash cat and john the ripper

Bcrypt, are designed so that hashing on a GPU does not provide any speed improvement over using a CPU; this helps them resist cracking.

`hashcat -m <hash_type> -a <attack_mode> hashfile wordlist`

- `-m <hash_type>` specifies the hash-type in numeric format. For example, `-m 1000` is for NTLM. Check the official documentation (`man hashcat`) and [example page (opens in new tab)](https://hashcat.net/wiki/doku.php?id=example_hashes) to find the hash type code to use.
- `-a <attack_mode>` specifies the attack-mode. For example, `-a 0` is for straight, i.e., trying one password from the wordlist after the other.
- `hashfile` is the file containing the hash you want to crack.
- `wordlist` is the security word list you want to use in your attack.

https://hashcat.net/wiki/doku.php?id=example_hashes 



![](../../assets/Pasted%20image%2020260808123849.png)


![](../../assets/Pasted%20image%2020260808123915.png)



![](../../assets/Pasted%20image%2020260808123933.png)

![](../../assets/Pasted%20image%2020260808124018.png)


![](../../assets/Pasted%20image%2020260808123952.png)


![](../../assets/Pasted%20image%2020260808124549.png)


![](../../assets/Pasted%20image%2020260808124602.png)

![](../../assets/Pasted%20image%2020260808124906.png)

![](../../assets/Pasted%20image%2020260808124925.png)

