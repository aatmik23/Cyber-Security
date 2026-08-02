
Whats the version and year of the windows machine? 

systeminfo 
osname


Which user logged in last?

`Get-WinEvent`

![241](../assets/Pasted%20image%2020260802211706.png)

![](../assets/Pasted%20image%2020260802212031.png)


 ![](../assets/Pasted%20image%2020260802212017.png)

![](../assets/Pasted%20image%2020260802212326.png)



`net user` is a built-in Windows Command Prompt command used to **view, create, modify, and manage local user accounts** on a Windows computer.

![](../assets/Pasted%20image%2020260802213040.png)

![](../assets/Pasted%20image%2020260802213105.png)

What IP does the system connect to when it first starts?

**remote machine the malware is trying to contact**.

boot ---> connect to attacker remote

system configration > regestiorEditor > 

HKEY_LOCAL_MACHINE
 └─ SOFTWARE
     └─ Microsoft
         └─ Windows
             └─ CurrentVersion
                 └─ Run

What is the `Run` key?

is a **special Windows Registry key**.

Windows checks this key **every time a user logs in**. Any program listed there is **automatically started**.

attacker use to run key

Windows starts
      ↓
Checks the Run key
      ↓
Finds UpdateSvc
      ↓
Runs nc.exe
      ↓
Connects to 10.34.2.3

![](../assets/Pasted%20image%2020260802215119.png)

What two accounts had administrative privileges

groups > administrator

![](../assets/Pasted%20image%2020260802220450.png)

![](../assets/Pasted%20image%2020260802220754.png)

Whats the name of the scheduled task that is malicous.

>task schedulor
>A **TMP folder** is used to store **temporary files** that programs or Windows create while they are running.

![](../assets/Pasted%20image%2020260802221650.png)

common path 
C:\Users\<username>\AppData\Local\Temp

During the compromise, at what time did Windows first assign special privileges to a new logon?

4672 special prvilage assign

![](../assets/Pasted%20image%2020260802233046.png)




![](../assets/Pasted%20image%2020260802234124.png)

|File Extension|Meaning|Runs With|
|---|---|---|

|   |   |   |
|---|---|---|
|`.exe`|Executable program|Windows|

|   |   |   |
|---|---|---|
|`.bat`|Batch script|Command Prompt (cmd)|

|   |   |   |
|---|---|---|
|`.ps1`|PowerShell script|PowerShell|

|   |   |   |
|---|---|---|
|`.py`|Python script|Python|


![](../assets/Pasted%20image%2020260802234809.png)

This is a **Windows hosts file**. It lets you manually map hostnames to IP addresses **before DNS is queried**.


![](../assets/Pasted%20image%2020260803000138.png)

![](../assets/Pasted%20image%2020260803000532.png)

**hosts file poisoning** or **hosts file hijacking**.

You type google.com
        │
        ▼
Check Hosts File
        │
        ▼
Found: google.com → 76.32.97.132
        │
        ▼
Connect to 76.32.97.132

which port was open firewall inbound

![](../assets/Pasted%20image%2020260803001342.png)


IIS (Internet Information Services) is ==a flexible, secure, and manageable web server software created by Microsoft that runs on the Windows operating system to host websites, services, and ASP.NET applications==. 

![](../assets/Pasted%20image%2020260803001634.png)



