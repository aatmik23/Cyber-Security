
Gerenal Information , MITRE and MAEC

The first block contains basic information about the file

- The cryptographic algorithms, such as the `md5`, and `sha1/256`.
- The `analysis` field tells us how CAPA performed its analysis on the file.
- The `os` field reveals the operating system () context for which the identified capabilities apply.
- The `arch` field allows us to determine whether we are dealing with a binary related to x86 architecture.
- The `path` where the analyzed file was located.


```powershell
┌─────────────┬────────────────────────────────────────────────────────────────────────────────────┐
│ md5         │ 3b9d26d2e7433749f2c32edb13a2b0a2                                                   │
│ sha1        │ 969437df8f4ad08542ce8fc9831fc49a7765b7c5                                           │
│ sha256      │ ae7bc6b6f6ecb206a7b957e4bb86e0d11845c5b2d9f7a00a482bef63b567ce4c                   │
│ analysis    │ static                                                                             │
│ os          │ windows                                                                            │
│ format      │ pe                                                                                 │
│ arch        │ i386                                                                               │
│ path        │ /home/strategos/Room-CAPA/cryptbot.bin                                             │
└─────────────┴────────────────────────────────────────────────────────────────────────────────────┘
```


### MITRE ATT&CK


MITRE ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge) framework is a comprehensive global knowledge repository that meticulously documents the tactics and techniques employed by threat actors at every stage of a cyber-attack


**aining initial access** to **maintaining a presence**, **escalating privileges**, **evading defenses**, **moving laterally within a network**, and much more.

| Format                                                                                                                     | Sample                                                                                   | Explanation                                                                                                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **ATT&CK Tactic**::**ATT&CK Technique**::**Technique Identifier**                                                          | Defense Evasion::Obfuscated Files or Information::T1027                                  | **DEFENSE EVASION =** ATT&CK Tactic  <br>**Obfuscated Files or Information =** ATT&CK Technique  <br>**T1027 =** Technique Identifier                                                                                                      |
| **ATT&CK Tactic**::**ATT&CK Technique**::**ATT&CK Sub-Technique**::**Technique Identifier**[.]Sub-technique **Identifier** | Defense Evasion::Obfuscated Files or Information::Indicator Removal from Tools T1027.005 | **DEFENSE EVASION** = ATT&CK Tactic  <br>**Obfuscated Files or Information** = ATT&CK Technique  <br>**Indicator Removal from Tools** = ATT&CK Sub-Technique  <br>**T1027 =** Technique Identifier  <br>**005** = Sub-Technique Identifier |


```powershell
┌──────────────────────┬───────────────────────────────────────────────────────────────────────────┐
│ ATT&CK Tactic        │ ATT&CK Technique                                                          │
├──────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ DEFENSE EVASION      │ Obfuscated Files or Information [T1027]                                   │
│                      │ Obfuscated Files or Information::Indicator Removal from Tools [T1027.005] │
│                      │ Virtualization/Sandbox Evasion::System Checks [T1497.001]                 │
│ DISCOVERY            │ File and Directory Discovery [T1083]                                      │
│ EXECUTION            │ Command and Scripting Interpreter::PowerShell [T1059.001]                 │
│                      │ Shared Modules [T1129]                                                    │
│ IMPACT               │ Resource Hijacking [T1496]                                                │
│ PERSISTENCE          │ Scheduled Task/Job::At [T1053.002]                                        │
│                      │ Scheduled Task/Job::Scheduled Task [T1053.005]                            │
└──────────────────────┴───────────────────────────────────────────────────────────────────────────┘
```


### MAEC


**Malware Attribute Enumeration and Characterization**

language designed to encode and communicate complex details concerning malware

**MAEC** stands for **Malware Attribute Enumeration and Characterization**.

It is a **standardized language/framework for describing malware and its characteristics**.

### In cybersecurity, MAEC is used to describe:

- **Malware behaviors** — what the malware does
- **Capabilities** — e.g., keylogging, file deletion, credential theft
- **Artifacts** — files, registry keys, mutexes, etc.
- **Relationships** — how different malware components or behaviors are connected
- **Indicators** associated with malware


|**MAEC Value**|Description|
|---|---|
|Launcher|Exhibits behaviours that trigger specific actions similar to malware behaviour.|
|Downloader|Exhibits behaviours wherein it downloads and executes other files, usually seen on more complex malware.|

![](../../assets/Pasted%20image%2020260812132839.png)


dditionally, when CAPA tags a file with a “**Downloader**” MAEC value, it indicates that the file demonstrates behaviour similar but not limited to:

- Fetching additional payloads or resources from the internet  
    
- pulling in updates
- executing secondary stages
- retrieving configuration files