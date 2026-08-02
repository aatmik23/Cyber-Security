
process of writing and executing a series of commands contained in a text file

For blue team professionals such as incident responders, malware analysts, and threat hunters, scripts can automate many different tasks, including log analysis, detecting anomalies, and extracting indicators of compromise (IOCs). These scripts can also be used to reverse-engineer malicious code (malware) or automate the scanning of systems for signs of intrusion.


For the **red team**, including penetration testers and ethical hackers, scripts can automate tasks like system enumeration, executing remote commands, and crafting obfuscated scripts to bypass defences. Its deep integration with all types of systems makes it a powerful tool for simulating attacks and testing systems’ resilience against real-world threats.


**system administrators** benefit from scripting for automating checks, managing system configurations, and securing networks, especially in remote or large-scale environments. scripts can be designed to enforce security policies, monitor systems health, and respond automatically to security incidents, thus enhancing the overall security posture.


`Invoke-Command` is essential for executing commands on remote systems, making it fundamental for system administrators, security engineers and penetration testers


efficient remote management and—combining it with scripting—automation of tasks across multiple machines.

execute payloads or commands on target systems

```powershell
PS C:\Users\captain> Get-Help Invoke-Command -examples

NAME
    Invoke-Command
    
SYNOPSIS
    Runs commands on local and remote computers.
    
    ------------- Example 1: Run a script on a server -------------
    
    Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
    
    The FilePath parameter specifies a script that is located on the local computer. The script runs on the remote computer and the results are returned to the local computer.

    --------- Example 2: Run a command on a remote server ---------

    Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }

    The ComputerName parameter specifies the name of the remote computer. The Credential parameter is used to run the command in the security context of Domain01\User01, a user who has permission to run commands. The ScriptBlock parameter specifies the command to be run on the remote computer.

    In response, PowerShell requests the password and an authentication method for the User01 account. It then runs the command on the Server01 computer and returns the result.
[...]
```


`Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01`

- **Invoke-Command** → Runs a command or script.
- **-FilePath c:\scripts\test.ps1** → Specifies a PowerShell script on **your local computer**.
- **-ComputerName Server01** → Tells PowerShell to execute that script on the remote computer named **Server01**.

`Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }`


- **-ComputerName Server01** → Target computer.
- **-Credential Domain01\User01** → Log in as `Domain01\User01`.
- **-ScriptBlock { Get-Culture }** → The command to execute remotely.


Computer (Machine):  Server01
Domain:              Domain01
Username:            User01


### Scenario 2: Same domain, but different account needed

Suppose you're logged in as:

```
THM\Bob
```

But only:

```
THM\Admin
```

has permission on `RoyalFortune`.

Then you **must** use:

```
Invoke-Command -ComputerName RoyalFortune -Credential THM\Admin -ScriptBlock { Get-Service }
```

Even though both computers are in the **same domain**, your current account doesn't have permission.




