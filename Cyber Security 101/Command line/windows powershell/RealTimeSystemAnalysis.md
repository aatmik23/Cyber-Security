
`get-process`

```powershell
PS C:\Users\captain> Get-Process

Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName 
-------  ------    -----      -----     ------     --  -- -----------
     67       5      872        500       0.06   2340   0 AggregatorHost
     55       5      712       2672       0.02   3024   0 AM_Delta_Patch_1.417.483.0
    309      13    18312       1256       0.52   1524   0 amazon-ssm-agent
     78       6     4440        944       0.02    516   0 cmd
     94       7     1224       1744       0.31    568   0 conhost
[...]
```

`Get-Service`

by forensics analysts hunting for anomalous services installed on the system.


```powershell
PS C:\Users\captain> Get-Service

Status   Name               DisplayName                           
------   ----               -----------
Stopped  Amazon EC2Launch   Amazon EC2Launch
Running  AmazonSSMAgent     Amazon SSM Agent
Stopped  AppIDSvc           Application Identity
Running  BFE                Base Filtering Engine
Running  CertPropSvc        Certificate Propagation
Stopped  ClipSVC            Client License Service (ClipSVC)
[...]
```



`Get-NetTCPConnection` displays current TCP connections, giving insights into both local and remote endpoints

handy during an incident response or malware analysis task, as it can uncover hidden backdoors or established connections towards an attacker-controlled server.


```powershell
PS C:\Users\captain> Get-NetTCPConnection

LocalAddress        LocalPort RemoteAddress       RemotePort State       AppliedSetting OwningProcess 
------------        --------- -------------       ---------- -----       -------------- -------------
[...]
::                  22        ::                  0          Listen                     1444          
10.10.178.209       49695     199.232.26.172      80         TimeWait                   0
0.0.0.0             49668     0.0.0.0             0          Listen                     424
0.0.0.0             49667     0.0.0.0             0          Listen                     652
0.0.0.0             49666     0.0.0.0             0          Listen                     388
0.0.0.0             49665     0.0.0.0             0          Listen                     560
0.0.0.0             49664     0.0.0.0             0          Listen                     672           
0.0.0.0             3389      0.0.0.0             0          Listen                     980
10.10.178.209       139       0.0.0.0             0          Listen                     4
0.0.0.0             135       0.0.0.0             0          Listen                     908
10.10.178.209       22        10.14.87.60         53523      Established Internet       1444
0.0.0.0             22        0.0.0.0             0 
```


`Get-FileHash`

a useful cmdlet for generating file hashes, which is particularly valuable in incident response, threat hunting, and malware analysis, as it helps verify file integrity and detect potential tampering.

```powershell
PS C:\Users\captain\Documents\captain-cabin> Get-FileHash -Path .\ship-flag.txt    

Algorithm       Hash                      Path 
---------       ----                      ----
SHA256          54D2EC3C12BF3D[...]       C:\Users\captain\Documents\captain-cabin\ship-flag.txt
```

**`Get-Item`** → Gets information about **one specific** file or folder.

```powershell
Get-Item -Path "C:\House\house_log.txt" -Stream *
```

```powershell
PS C:\Users\Alex\Documents> Get-Item -Path "C:\House\house_log.txt" -Stream *PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\House\house_log.txt::$DATAPSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\HousePSChildName   : house_log.txt::$DATAPSDrive       : CPSProvider    : Microsoft.PowerShell.Core\FileSystemPSIsContainer : FalseFileName      : C:\House\house_log.txtStream        : :$DATALength        : 13PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\House\house_log.txt:housinginfoPSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\HousePSChildName   : house_log.txt:housinginfoPSDrive       : CPSProvider    : Microsoft.PowerShell.Core\FileSystemPSIsContainer : FalseFileName      : C:\House\house_log.txtStream        : housinginfoLength        : 21
```


- `:$DATA` is the default data stream of every NTFS file. It contains the normal file contents and is not an ADS.
    
- `housinginginfo` is the Alternate Data Stream (ADS) added to this file. It appears as `house_log.txt:housinginfo`, which means an extra hidden stream named housinginfo is attached to this file.


- ❌ A stream is **not just a shortcut or pointer**.
- ✅ A stream **contains its own data**.
- ✅ NTFS keeps track of all the streams that belong to a file.


### Compare it to a folder

Imagine a folder:

```
Folder
├── file1.txt
├── file2.txt
└── file3.txt
```

A file with ADS is somewhat similar:

```
notes.txt
├── $DATA
├── Secret
└── Zone.Identifier
```
