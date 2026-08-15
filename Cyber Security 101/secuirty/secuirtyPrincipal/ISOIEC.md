
International Organization for Standardization (ISO) and the International Electrotechnical Commission (IEC) have created the ISO/IEC 19249.



### Domain Separation

**Meaning:** Separate things into different security areas (domains) and give each area its own permissions.

Example in a CPU:

```
Ring 0 → OS Kernel → HIGH privilege
Ring 3 → User applications → LOW privilege
```

A normal application running in **Ring 3** should not be able to directly perform privileged kernel operations.

**Easy idea:**  
👉 **Keep different things in separate security zones.**

---

### 2. Layering

**Meaning:** Divide a system into multiple layers, where each layer has a specific job.

For example, the OSI model:

```
Application
Presentation
Session
Transport
Network
Data Link
Physical
```

Each layer interacts mainly with the layer next to it.

In security, this helps because you can apply security controls at **multiple layers**.

This is related to **Defense in Depth**:

```
Firewall
   ↓
Authentication
   ↓
Application security
   ↓
Database permissions
   ↓
Encryption
```

If one security layer fails, another may still protect you.

**Easy idea:**  
👉 **Don't depend on one security layer. Use multiple layers.**

---

### 3. Encapsulation

**Meaning:** Hide the internal details of something and allow access through controlled methods/interfaces.

Example:

```
Clock
 ├── seconds  ← hidden
 └── increment() ← allowed method
```

Instead of letting a program directly change:

```
seconds = -500
```

it uses:

```
increment()
```

The function can make sure the value stays valid.

In cybersecurity, APIs work similarly:

```
Application
     ↓
   API
     ↓
 Database
```

The application doesn't directly manipulate the database's internal mechanisms.

**Easy idea:**  
👉 **Hide the inside; provide a controlled way to interact with it.**

---

### 4. Redundancy

**Meaning:** Have a backup so that if one component fails, another can continue working.

Example:

```
Server
 ├── Power Supply 1 ✅
 └── Power Supply 2 ✅
```

If Power Supply 1 fails:

```
Power Supply 1 ❌
Power Supply 2 ✅ → Server keeps running
```

RAID can also provide redundancy.

This mainly helps with:

- **Availability** → system stays operational
- **Integrity** → some systems can detect corrupted/changed data

**Easy idea:**  
👉 **Have backups/replacements so one failure doesn't bring everything down.**

---

### 5. Virtualization

**Meaning:** Use software to create separate virtual environments on the same physical hardware.

For example:

```
Physical computer
       ↓
   Hypervisor
   /        \
 VM 1       VM 2
Linux      Windows
```

The VMs are separated from each other.

In malware analysis, you can use a **virtual machine as a sandbox**:

```
Your real computer
       ↓
   Virtual Machine
       ↓
   Malware sample
```

If the malware executes inside the VM, the VM provides an additional security boundary between the malware and your main system.


ISO/IEC 19249 teaches five _design_ principles:

**Least Privilege**

if a user needs to be able to view a document, you should give them read rights without write rights.

**Attack Surface Minimisation**:

vulnerabilities represent risks that we should aim to minimize

**Centralized Parameter Validation**

userinput --> dos --> remote excution

Considering the number of parameters a system handles, the validation of the parameters should be centralized within one library or system.

**Centralized General Security Services**:

would create a centralized server for authentication. Of course, you might take proper measures to ensure availability and prevent creating a single point of failure.

**Preparing for Error and Exception Handling**:

