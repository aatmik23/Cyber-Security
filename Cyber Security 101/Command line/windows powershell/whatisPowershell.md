is a powerful tool from Microsoft designed for task automation and configuration management. It combines a command-line interface and a scripting language built on the .NET framework.

PowerShell exists because **Command Prompt (CMD) is limited**. Microsoft created PowerShell to make system administration and automation much more powerful.

Here's a comparison:

|CMD|PowerShell|
|---|---|
|Basic commands|Advanced administration|
|Works mostly with text|Works with **objects** (structured data)|
|Limited scripting|Powerful scripting language|
|Basic file operations|Can manage Windows, Active Directory, Registry, Services, Azure, Microsoft 365, and more|

## The Power in PowerShell

, an **object** represents an item with **properties** (characteristics) and **methods** (actions).

Instead, when a **cmdlet** (pronounced _command-let_) is run in powershell , it returns objects that retain their properties and methods

Cmdlets follow a consistent `Verb-Noun` naming convention. This structure makes it easy to understand what each cmdlet does. The `Verb` describes the action, and the `Noun` specifies the object on which action is performed. For example:


- `Get-Content`: Retrieves (gets) the content of a file and displays it in the console.
- `Set-Location`: Changes (sets) the current working directory


## Basic Cmdlets


`Get-Command`. It’s an essential tool for discovering what commands one can use.

![](../../assets/Pasted%20image%2020260802013346.png)

display only the available commands of type “function”, we can use `-CommandType "Function"`

![](../../assets/Pasted%20image%2020260802013710.png)

get-help

![](../../assets/Pasted%20image%2020260802013816.png)

For example, by appending `-examples`



The cmdlet to list files is:

```
Get-ChildItem
```

PowerShell provides the alias:

```
dir
```


![](../../assets/Pasted%20image%2020260802014110.png)


search module and download it 

```powershell
Find-Module -Name "PowerShell*"
```

```powershell
Install-Module -Name "PowerShellGet"
```

