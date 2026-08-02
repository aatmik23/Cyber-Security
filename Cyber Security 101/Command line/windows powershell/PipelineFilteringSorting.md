
by the `|` symbol, piping 

```powershell
Get-ChildItem | Sort-Object Length
```

- `Name` – File name
- `FullName` – Full path
- `Length` – File size (in bytes)
- `Extension` – File extension
- `CreationTime` – When the file was created
- `LastWriteTime` – When the file was last modified
![](../../assets/Pasted%20image%2020260802020849.png)

- `-ne`: "**not equal**". This operator can be used to exclude objects from the results based on specified criteria.
- `-gt`: "**greater than**". This operator will filter only objects which exceed a specified value. It is important to note that this is a strict comparison, meaning that objects that are equal to the specified value will be excluded from the results.
- `-ge`: "**greater than or equal to**". This is the non-strict version of the previous operator. A combination of `-gt` and `-eq`.
- `-lt`: "**less than**". Like its counterpart, "greater than", this is a strict operator. It will include only objects which are strictly below a certain value.
- `-le`: "**less than or equal to**". Just like its counterpart `-ge`, this is the non-strict version of the previous operator. A combination of `-lt` and `-eq`.



(`-like`


![](../../assets/Pasted%20image%2020260802021046.png)


`Select-Object`

![](../../assets/Pasted%20image%2020260802021148.png)