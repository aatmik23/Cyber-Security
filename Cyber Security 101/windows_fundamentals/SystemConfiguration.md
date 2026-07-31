
`MSConfig` advanced troubleshooting, and its main purpose is to help diagnose startup issues.

- General
we can select what devices and services for Windows to load upon boot. The options are: **Normal**, **Diagnostic**, or **Selective**.

- Boot
- Services
**Services** tab lists all services configured for the system regardless of their state (running or stopped).

- Startup
- Tools
A service is a special type of application that runs in the background.

## Advanced System Settings

`View advanced system settings`


use to control the performance behavior and system recovery.

a page file as an extra virtual memory space when the physical RAM becomes full. 

![](../assets/Pasted%20image%2020260731142937.png)

![](../assets/Pasted%20image%2020260731143037.png)


Startup and Recovery.

windows can create a crash dump file whenever it encounters a critical error, such as a Blue Screen of Death

![](../assets/Pasted%20image%2020260731143235.png)

Windows supports different dump types, such as:

- Automatic memory dump
- Kernel memory dump
- Small memory dump (256 KB)
- Complete memory dump
- None

a **dump** is a **copy of data** taken from memory, a program, or a storage device for analysis, debugging, or backup.

Security analysts use memory dumps to:

- Find malware.
- Recover passwords or encryption keys.
- Investigate crashes.
- Analyze running processes.

---**LSASS dump** → Copy of the memory of the `lsass.exe` process, which may contain credentials. (This is a common technique in authorized penetration testing and incident response, but it should only be performed on systems you own or have permission to test.)