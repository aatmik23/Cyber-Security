
`/etc/snort`

commonly uses `/usr/local/etc/snort`, while this machine uses `/etc/snort`.

The key file for Snort is its configuration file `snort.lua`, where you can specify which rule files to enable, which network range to monitor, and allow other settings.


. The rule files are stored in the `rules` folder. Let's use the `ls` command to list all the files and folders present in Snort's main directory:

location is used, you load a configuration by passing its path to the `-c` flag


## Rule Format


![](../../assets/Pasted%20image%2020260811234751.png)

**Rule metadata:** Every rule has some metadata. That is defined at the end of the rule in parentheses. The following are its components:

- **Message (msg):** This describes the message displayed when the subject rule triggers. The message should indicate the type of activity detected. In this case, we used "Ping Detected".
- **Signature ID (sid):** Every rule has a unique identifier that differentiates it from others. This identifier is called the signature ID (sid). In this case, we set the sid to "10001".
- **Rule revision (rev):** This sets the rule's revision number. Every time the rule is modified, its revision number is incremented, which helps in tracking changes to any rule.

```shell-session
ubuntu@tryhackme:~$ sudo nano /etc/snort/rules/local.rules
```


![](../../assets/Pasted%20image%2020260811235055.png)


## Rule Testing


```shell-session
ubuntu@tryhackme:~$ sudo snort -q -l /var/log/snort -i lo -A alert_fast -c /etc/snort/snort.lua
```





![](../../assets/Pasted%20image%2020260811235525.png)



```shell-session
sudo snort -q -l /var/log/snort -r Task.pcap -A alert_fast -c /etc/snort/snort.lua
```

	**Note:** Replace the "Task.pcap" with the path to your file for analysis.