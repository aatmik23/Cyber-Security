
task 

current ad 


![](../assets/Pasted%20image%2020260731223655.png)

goal

![](../assets/Pasted%20image%2020260731223707.png)


deleteion 

![](../assets/Pasted%20image%2020260731223731.png)

disbale accidental deletion from view enalble advance feature

![](../assets/Pasted%20image%2020260731223955.png)

delegation

One of the nice things you can do in is to give specific users some control over some OUs. This process is known as **delegation** and allows you to grant users specific privileges to perform advanced tasks on OUs without needing a Domain Administrator to step in.

![](../assets/Pasted%20image%2020260731235519.png)
![](../assets/Pasted%20image%2020260731235544.png)


![](../assets/Pasted%20image%2020260801003319.png)


![](../assets/Pasted%20image%2020260801010615.png)


```shell-session
PS C:\Users\phillip> Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose

New Password: *********

VERBOSE: Performing the operation "Set-ADAccountPassword" on target "CN=Sophie,OU=Sales,OU=THM,DC=thm,DC=local".
```

wouldn't want Sophie to keep on using a password we know,

```shell-session
PS C:\Users\phillip> Set-ADUser -ChangePasswordAtLogon $true -Identity sophie -Verbose

VERBOSE: Performing the operation "Set" on target "CN=Sophie,OU=Sales,OU=THM,DC=thm,DC=local".
```

