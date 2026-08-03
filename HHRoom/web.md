find / -iname "common.txt" 2>/dev/null

Every Linux program has three standard streams:

| Number | Name   | Purpose        |
| ------ | ------ | -------------- |
| 0      | stdin  | Input          |
| 1      | stdout | Normal output  |
| 2      | stderr | Error messages |
`/dev/null` is a special file known as the **null device**.

Anything written to it is immediately discarded.

Think of it as a **black hole**.




 nmap -sC -sV -oN nmap/initial 10.49.133.129


If the `nmap` directory exists, you'll get a file like:

```
nmap/
└── initial
```

Instead of only printing the results on the screen, Nmap also saves them for later reference.



feroxbuster -u http://10.49.133.129:8080 -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt


pip install git-dumper

`git-dumper` is a tool used to **reconstruct a Git repository** when a website accidentally exposes its `.git` directory


git-dumper http://10.49.133.129:8080/.git loot

reconstruct it in a local directory named `loot`."



ls -la loot

`-l` means **long listing format**.
`-a` means **all**. 

