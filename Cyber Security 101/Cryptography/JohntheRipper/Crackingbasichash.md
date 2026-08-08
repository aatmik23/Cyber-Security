
**P = easy to solve**  
**NP = easy to check**


`john [options] [file path]`

- `john`: Invokes the John the Ripper program
- `[options]`: Specifies the options you want to use
- `[file path]`: The file containing the hash you’re trying to crack; if it’s in the same directory, you won’t need to name a path, just the file.


`john --wordlist=[path to wordlist] [path to file]`

- `--wordlist=`: Specifies using mode, reading from the file that you supply in the provided path
- `[path to wordlist]`: The path to the you’re using, as described in the previous task

	to find hash algo use hashes.com OR [hash-identifier (opens in new tab)](https://gitlab.com/kalilinux/packages/hash-identifier/-/tree/kali/master), a Python tool that is super easy to use and will tell you what different types of hashes


`john --format=[format] --wordlist=[path to wordlist] [path to file]`

- `--format=`: This is the flag to tell John that you’re giving it a hash of a specific format and to use the following format to crack it
- `[format]`: The format that the hash is in

**Example Usage:**

`john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt`


`john --list=formats` and either check manually or grep for your hash type using something like `john --list=formats | grep -iF "md5"`.


![](../../assets/Pasted%20image%2020260808203644.png)


![](../../assets/Pasted%20image%2020260808203745.png)


![](../../assets/Pasted%20image%2020260808204618.png)


![](../../assets/Pasted%20image%2020260808204631.png)


![](../../assets/Pasted%20image%2020260808204731.png)


![](../../assets/Pasted%20image%2020260808204742.png)


![](../../assets/Pasted%20image%2020260808205817.png)


![](../../assets/Pasted%20image%2020260808205811.png)



D7F4D3CCEE7ACD3DD7FAD3AC2BE2AAE9C44F4E9B7FB802D73136D4C53920140A


c5a60cc6bbba781c601c5402755ae1044bbf45b78d1183cbf2ca1c865b6c792cf3c6b87791344986c8a832a0f9ca8d0b4afd3d9421a149d57075e1b4e93f90bf

![](../../assets/Pasted%20image%2020260808210035.png)


![](../../assets/Pasted%20image%2020260808210343.png)

sha512 is not working so it is whirlpool

