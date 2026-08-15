
 **C:\Users\Administrator\Desktop\Sample** folder.  

**windows.exe**  




![](../../assets/Pasted%20image%2020260813174947.png)




![](../../assets/Pasted%20image%2020260813174901.png)


### Think of it this way

**Windows Registry** = a huge database containing Windows settings.

**Regedit** = the program you use to look inside and modify that database.### Think of it this way

**Windows Registry** = a huge database containing Windows settings.

**Regedit** = the program you use to look inside and modify that database.


REGEDIT tools are usually found in the **C:\Windows\System32** directory rather than the user's download location.


### Rich Header

- **Rich Header** = contains information about the tools/compiler used to build a Windows PE file.
    
- **Missing Rich Header** = can be a clue that the file was **packed, modified, or obfuscated**.
    
- ⚠️ **Not proof of malware** — use other indicators to confirm.
    
- **Purpose of packing** = hide the original code and make static analysis harder.

![](../../assets/Pasted%20image%2020260813180301.png)


Редактор реестра" - "Registry Editor", "Операционная система Microsoft® Windows®") in the file’s metadata is suspicious, primarily if the user or the organization does not operate in a Russian-speaking environment. This could potentially have profound implications for our organization.


**function** tabs list **API calls** that the file has imported. This is also known as the IAT (Import Address Table)


![](../../assets/Pasted%20image%2020260813180549.png)


![](../../assets/Pasted%20image%2020260813180649.png)

`set_UseShellExecute`: This function allows the process to use the operating system's shell to execute other processes. This is often seen in malware that spawns additional processes to carry out malicious actions


`CryptoStream, RijndaelManaged, CipherMode, CreateDecryptor`: These APIs indicate that the executable uses cryptographic functions, specifically Rijndael (AES encryption). Malware may use cryptography to encrypt communication and files or even implement ransomware functionality.

use floss to extract strings 
floss.exe .\windows.exe > windows.txt


![](../../assets/Pasted%20image%2020260813181352.png)


## Analyze with Process Explorer and Process Monitor


![](../../assets/Pasted%20image%2020260813182547.png)

![](../../assets/Pasted%20image%2020260813182607.png)


![](../../assets/Pasted%20image%2020260813182932.png)

![](../../assets/Pasted%20image%2020260813182945.png)

### Entropy value

Entropy ranges from:

**0 → 8**

- **Low entropy (~0–4)** → data is more predictable/plain
- **Medium (~4–6)** → normal-looking data
- **High (~7–8)** → very random-looking data

In malware analysis, **high entropy can indicate packing or encryption**, because packed/encrypted data tends to look random.


![](../../assets/Pasted%20image%2020260813183300.png)


`requestedExecutionLevel` tells Windows **what privilege level the program requests**.

Common values are:

- **`asInvoker`** → run with the same privileges as the user who launched it.
- **`highestAvailable`** → request the highest privileges available to the user.
- **`requireAdministrator`** → **requires administrator privileges**; Windows will prompt for elevation

![](../../assets/Pasted%20image%2020260813183456.png)


imported hash (imphash)

**Imphash** is a **fingerprint of the functions a program uses**.

For example, a program may use:

```
CreateFile
ReadFile
WriteFile
```

These imported functions are used to create an **Imphash**.


![](../../assets/Pasted%20image%2020260813184217.png)


A **defanged IP address** is an IP address written in a way that **prevents accidentally connecting to it**.

### Normal IP

```
192.168.1.10
```

### Defanged IP

```
192[.]168[.]1[.]10
```

The `.` is replaced with `[.]`.


![](../../assets/Pasted%20image%2020260813184916.png)



**C2 IP address** means the **IP address of a Command-and-Control (C2) server**.


![](../../assets/Pasted%20image%2020260813190506.png)

