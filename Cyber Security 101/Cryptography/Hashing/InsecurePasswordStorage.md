
**three insecure practices** when it comes to passwords:

- Storing passwords in plaintext
- Storing passwords using a deprecated encryption
- Storing passwords using an insecure hashing algorithm


A **Rainbow Table** is a lookup table of hashes to plaintexts, so you can quickly find out what password a user had just from the hash.

| Hash                             | Password  |
| -------------------------------- | --------- |
| 02c75fb22c75b23dc963c7eb91a062cc | zxcvbnm   |
| b0baee9d279d34fa1dfd71aadb908c3f | 11111     |
| c44a471bd78cc6c2fea32b9fe028d30a | asdfghjkl |
|                                  |           |


crackstation hasesh.com

the salt is a randomly generated value stored in the database and should be unique to each user.


Hash functions like Bcrypt and Scrypt handle this automatically. Salts don’t need to be kept private.


![](../../assets/Pasted%20image%2020260808115859.png)