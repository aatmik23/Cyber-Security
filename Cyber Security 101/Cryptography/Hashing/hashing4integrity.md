


### HMACs

**HMAC (Keyed-Hash Message Authentication Code)** is a type of message authentication code (MAC) that uses a cryptographic hash function in combination with a secret key to verify the authenticity and of data

| Method            | Secret key?            | Main purpose                                            |
| ----------------- | ---------------------- | ------------------------------------------------------- |
| SHA-256           | ❌                      | Detect changes                                          |
| HMAC-SHA256       | ✅                      | Detect changes + authenticate someone who knows the key |
| Digital signature | 🔑 Private/public keys | Detect changes + authenticate signer                    |
![](../../assets/Pasted%20image%2020260808125653.png)


![](../../assets/Pasted%20image%2020260808125942.png)



**Encoding** converts data from one form to another to make it compatible with a specific system. ASCII, UTF-8, UTF-16, UTF-32, ISO-8859-1, and Windows-1252 are valid encoding methods for the English language. Note that UTF-8, UTF-16, and UTF-32 are Unicode encodings, and they can represent characters from other languages, such as Arabic and Japanese.

- **ASCII** → mainly English characters
- **UTF-8** → supports English + Arabic + Japanese + almost all languages
- **UTF-16 / UTF-32** → other Unicode formats
- **ISO-8859-1** → Western European characters
- **Windows-1252** → Windows character encoding



### Base64 / Base32

These are different.

They aren't designed for a particular language. They convert **binary data into printable characters**.

For example:

```
Hello
```

Base64 encoding gives:

```
SGVsbG8=
```

And decoding reverses it:

```
SGVsbG8= → Hello
```


![](../../assets/Pasted%20image%2020260808130625.png)