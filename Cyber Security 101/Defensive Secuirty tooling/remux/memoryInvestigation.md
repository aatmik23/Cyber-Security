
The analyst often relies on tools such as Volatility when dealing with memory images as evidence.


`vol3 -f wcry.mem`.  add plugins to investegate



### PsTree

This plugin lists processes in a tree based on their parent process ID.

![](../../assets/Pasted%20image%2020260813122843.png)


### PsList

This plugin is used to list all currently active processes in the machine.


```powershell
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ vol3 -f wcry.mem windows.pslist.PsList
Volatility 3 Framework 2.0.0
Progress:  100.00		PDB scanning finished
```

![](../../assets/Pasted%20image%2020260813122938.png)

### CmdLine

This plugin is used to list process command line arguments.


```powershell
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ vol3 -f wcry.mem windows.cmdline.CmdLine
Volatility 3 Framework 2.0.0
Progress:  100.00		PDB scanning finished
```

![](../../assets/Pasted%20image%2020260813123007.png)


### FileScan

This plugin scans for file objects in a particular Windows memory image. The results have more than 1,400 lines.

Terminal

```powershell
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ vol3 -f wcry.mem windows.filescan.FileScan
Volatility 3 Framework 2.0.0
Progress:  100.00		PDB scanning finished
```


![](../../assets/Pasted%20image%2020260813123132.png)


### DllList

This plugin lists the loaded modules in a particular Windows memory image. 

```powershell
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ vol3 -f wcry.mem windows.dlllist.DllList
Volatility 3 Framework 2.0.0
Progress:  100.00		PDB scanning finished
```



### PsScan

This plugin is used to scan for processes present in a particular Windows memory image.

Terminal

```powershell
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ vol3 -f wcry.mem windows.psscan.PsScan
Volatility 3 Framework 2.0.0
Progress:  100.00		PDB scanning finished
```


![](../../assets/Pasted%20image%2020260813123443.png)


### Malfind

This plugin is used to lists process memory ranges that potentially contain injected code. There won't be any View Results icon for this one due to text limitation.

Terminal

```powershell
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ vol3 -f wcry.mem windows.malfind.Malfind
Volatility 3 Framework 2.0.0
Progress:  100.00		PDB scanning finished
```



```powershell
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ for plugin in windows.malfind.Malfind windows.psscan.PsScan windows.pstree.PsTree windows.pslist.PsList windows.cmdline.CmdLine windows.filescan.FileScan windows.dlllist.DllList; do vol3 -q -f wcry.mem $plugin > wcry.$plugin.txt; done
```


`-q`, which means quiet mode or does not show the progress in the terminal



### Preprocessing With Strings

Next, we will preprocess the memory image with the Linux strings utility. We will extract the **ASCII**, 16-bit **little-endian**, and 16-bit **big-endian** strings. See the command below.

Terminal

```powershell
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ strings wcry.mem > wcry.strings.ascii.txt
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ strings -e l  wcry.mem > wcry.strings.unicode_little_endian.txt
root@10.49.151.136:/home/ubuntu/Desktop/tasks/Wcry_memory_image$ strings -e b  wcry.mem > wcry.strings.unicode_big_endian.txt
```