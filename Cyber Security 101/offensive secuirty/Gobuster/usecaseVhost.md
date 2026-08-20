
Virtual hosts are different websites on the same machine. Sometimes, they look like subdomains, but don’t be deceived! Virtual hosts are IP-based and are running on the same server.

Subdomains are set up in DNS. The  difference between `vhost` and `dns` mode is in the way Gobuster scans:

- `vhost` mode will navigate to the URL created by combining the configured HOSTNAME (-u flag) with an entry of a wordlist.
- `dns` mode will do a lookup to the FQDN created by combining the configured domain name (-d flag) with an entry of a .


```
gobuster vhost -u "http://example.thm" -w /path/to/wordlist
```


```shell-session
root@tryhackme:~# gobuster vhost -u "http://10.49.157.75" --domain example.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt --append-domain --exclude-length 250-320 
```

![](../../assets/Pasted%20image%2020260820202916.png)


![](../../assets/Pasted%20image%2020260820202927.png)

