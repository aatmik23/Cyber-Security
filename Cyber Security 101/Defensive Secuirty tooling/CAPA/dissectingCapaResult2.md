```powershell
┍━━━━━━━━━━━━━━━┯━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┑
	│ MBC Objective               │ MBC Behavior                                                                  │
	┝━━━━━━━━━━━━━━━┿━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┥
	│ ANTI-BEHAVIORAL ANALYSIS    │ Lab Machine Detection [B0009]
    ├─────────────────────────────┼───────────────────────────────━──────────────────────────────────────────────┤
	│ ANTI-STATIC ANALYSIS        │ Executable Code Obfuscation::Argument Obfuscation [B0032.020]                 │
	│                             │ Executable Code Obfuscation::Stack Strings [B0032.017]                        │
	├─────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
	│ COMMUNICATION               │ HTTP Communication [C0002]                                                    │
	│                             │ HTTP Communication::Read Header [C0002.014]                                   │
	├─────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
	│ DATA                        │ Check String [C0019]                                                          │
	│                             │ Encode Data::Base64 [C0026.001]                                               │
	│                             │ Encode Data::XOR [C0026.002]                                                  │
	├─────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
	│ DEFENSE EVASION             │ Obfuscated Files or Information::Encoding-Standard Algorithm [E1027.m02]      │
	├─────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
	│ DISCOVERY                   │ File and Directory Discovery [E1083]                                          │
	├─────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
	│ EXECUTION                   │ Command and Scripting Interpreter [E1059]                                     │
	├─────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
	│ FILE SYSTEM                 │ Create Directory [C0046]                                                      │
	│                             │ Delete File [C0047]                                                           │
	│                             │ Read File [C0051]                                                             │
	│                             │ Writes File [C0052]                                                           │
	├─────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
	│ MEMORY                      │ Allocate Memory [C0007]                                                       │
	├─────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
	│ PROCESS                     │ Create Process [C0017]                                                        │
	┕━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┷━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┙
```


### Malware Behavior Catalogue MBC

**MBC** in malware analysis usually means **Malware Behavior Catalog**.

It is a framework used to describe **what malware does**, rather than just identifying the malware family.

For example, MBC can describe behaviors such as:

- **Process Injection** → malware injects code into another process.
- **File Deletion** → malware deletes files.
- **Command Execution** → malware executes commands.
- **Credential Theft** → malware attempts to obtain credentials.
- **Network Communication** → malware communicates with another system.
- **Persistence** → malware tries to remain active after reboot.


![](../../assets/Pasted%20image%2020260812135043.png)


### Objective

The Objective are based on **ATT&CK tactics in the context of malware behaviou**



| **Objective**                | **Explanation**                                                                                                                                                                                                                                                                                                                                          |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Anti-Behavioral Analysis** | Malware attempts to avoid detection by hindering behavioural analysis using tools like sandboxes or debuggers.                                                                                                                                                                                                                                           |
| **Anti-Static Analysis**     | Malware attempts to obstruct or add complexity to static analysis , making it more challenging for security professionals to identify and understand its malicious behaviours and intentions.                                                                                                                                                            |
| **Collection**               | Malware focuses on identifying and gathering information from the targeted machine or network.                                                                                                                                                                                                                                                           |
| **Command and Control**      | Malware typically establishes communication with compromised systems through various methods such as command and control servers, peer-to-peer networks, or other means. This communication allows the malware to control the compromised systems, enabling the attackers to execute commands, exfiltrate data, or carry out other malicious activities. |
| **Credential Access**        | The primary aim of malware is to steal account credentials, such as usernames and passwords.                                                                                                                                                                                                                                                             |
| **Defense Evasion**          | The malware aims to bypass and circumvent the various detection and security mechanisms present within the system to avoid being detected or mitigated.                                                                                                                                                                                                  |


|                          |                                                                                                                                                                                                                                                                                  |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Discovery**            | Malware Seeks to collect detailed information about the configuration and setup of the system or network environment, including hardware, software, and network infrastructure.                                                                                                  |
| **Execution**            | Malware is designed to execute unauthorized commands or code on a targeted computer system without the user’s consent. This can include a wide range of harmful activities, such as stealing personal information, damaging files, or gaining unauthorized access to the system. |
| **Exfiltration**         | Malware is designed to infiltrate computer systems or networks to steal and extract sensitive data. This can include personal information, financial details, and any other valuable data stored on the targeted system or network.                                              |
| **Impact**               | Malware aims to manipulate, disrupt, or damage computer systems and data. It can enter computers through infected emails, compromised websites, and other deceptive means, leading to financial loss, privacy breaches, and system instability.                                  |
| **Lateral Movement**     | Malware seeks to spread through the network, either actively through machine access or passively, such as via malicious emails.                                                                                                                                                  |
| **Persistence**          | Malware is intentionally developed with the capability to remain undetected and operational on a computer system for an extended period.                                                                                                                                         |
| **Privilege Escalation** | Malware seeks to infiltrate a computer system or network to gain elevated permissions or control. Once inside the target environment, malware can seek to escalate its privileges, access sensitive information, or take control of system resources for malicious purposes.     |


### Micro-Objective

| **Micro-Objective** | **Description**                                                                                                                                          |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **PROCESS**         | exhibiting behaviours related to processes such as but not limited to Creating Process, Setting Thread Context, Terminating Process, and Checking Mutex. |
| **MEMORY**          | exhibiting behaviours such as, but not limited to, Allocating Memory, Changing Memory Protection, and Freeing Memory.                                    |
| **COMMUNICATION**   | exhibiting behaviours such as (not limited to (DNS, FTP, , ICMP, SMTP) network traffic.                                                                  |
| **DATA**            | exhibiting behaviours such as but not limited to Checking strings, compressing, decoding and encoding data                                               |

## MBC Behaviour

![](../../assets/Pasted%20image%2020260812150658.png)


method



![](../../assets/Pasted%20image%2020260812150819.png)