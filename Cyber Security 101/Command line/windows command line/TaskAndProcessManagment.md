`tasklist`

![](../../assets/Pasted%20image%2020260802005434.png)

we want to search for tasks related to `sshd.exe`

`tasklist /FI "imagename eq sshd.exe"`

`/FI`  filter _image name equals_ `sshd.exe`.

![](../../assets/Pasted%20image%2020260802005618.png)

`taskkill /PID target_pid`

- `chkdsk`: checks the file system and disk volumes for errors and bad sectors.
- `driverquery`: displays a list of installed device drivers.
- `sfc /scannow`: scans system files for corruption and repairs them if possible.


- Display text files: `more file.txt`
- Pipe long output to view it page by page: `some_command | more`


|   |   |
|---|---|
|`shutdown /s`|Shut down the computer|

|   |   |
|---|---|
|`shutdown /r`|Restart the computer|

|   |   |
|---|---|
|`shutdown /l`|Log off the current user|

|               |                                     |
| ------------- | ----------------------------------- |
| `shutdown /a` | Abort a pending shutdown or restart |