
**Enumeration**

Enumeration is the act of listing all the available resources, whether they are accessible or not. For example, Gobuster enumerates web directories.

**Brute Force**

Brute force is the act of trying every possibility until a match is found.

enumerating directories, files, DNS subdomains, Google Cloud Storage buckets, and Amazon S3 bucket


```
gobuster dir -u "http://www.example.thm/" -w /usr/share/wordlists/dirb/small.txt -t 64
```

