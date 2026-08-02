
dir --> ls

dir === `Get-ChildItem`

![](../../assets/Pasted%20image%2020260802015142.png)


cd ---> `Set-Location`

![](../../assets/Pasted%20image%2020260802015338.png)

`New-Item`  to create file and directory

![](../../assets/Pasted%20image%2020260802015729.png)

`Remove-Item`

same

using respectively `Copy-Item` (equivalent to `copy`) and `Move-Item` (equivalent to `move`).

```powershell
Copy-Item -Path .\captain-cabin\captain-hat.txt -Destination .\captain-cabin\captain-hat2.txt
PS C:\Users\captain\Documents> Get-ChildItem -Path ".\captain-cabin\" 

    Directory: C:\Users\captain\Documents\captain-cabin

Mode                 LastWriteTime         Length Name 
----                 -------------         ------ ----
d-----          9/4/2024  12:50 PM                captain-wardrobe
-a----          9/4/2024  12:50 PM              0 captain-boots.txt
-a----          9/4/2024  12:14 PM            264 captain-hat.txt
-a----          9/4/2024  12:14 PM            264 captain-hat2.txt
-a----          9/4/2024  12:37 PM           2116 ship-flag.txt 
```

```powershell
Get-Content -Path ".\captain-hat.txt"
```

![](../../assets/Pasted%20image%2020260802015952.png)


