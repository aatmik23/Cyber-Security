Windows  is the **New Technology file system** or simply  ntfs

Before , there was  **FAT16/FAT32** (File Allocation Table) and **HPFS** (High Performance ).

**ntfs**  automatically repair the folders/files on disk using information stored in a log file.

- Supports files larger than 4GB
- Set specific permissions on folders and files
- Folder and file compression
- Encryption file system or efs


The permissions are:

- **Full control**
- **Modify**
- **Read & Execute**
- **List folder contents**
- **Read**
- **Write**
![](../assets/Pasted%20image%2020260731123744.png)

![](../assets/Pasted%20image%2020260731123805.png)



Another feature of NTFS is **Alternate Data Streams** ( **ADS** ).

message.txt
        │
        ▼
Default Stream
This is Linux.

with ads

message.txt
        │
        ├────────────► Default Stream
        │               This is Linux.
        │
        └────────────► Alternate Stream
                        Secret Password

malware writers have used ADS to hide data.
