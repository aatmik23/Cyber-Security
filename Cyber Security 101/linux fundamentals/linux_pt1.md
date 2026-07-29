|          |                                                                                                                                                                                                                                   |
| -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `whoami` | tells you who you are on the system                                                                                                                                                                                               |
| `echo`   | output some specific text that is provided                                                                                                                                                                                        |
| `ls`     | list what's in the current folder                                                                                                                                                                                                 |
| `cd`     | change directory — move into a folder                                                                                                                                                                                             |
| `cat`    | show the contents of a file                                                                                                                                                                                                       |
| `pwd`    | print working directory — "where am I?"                                                                                                                                                                                           |
| `find`   | search for files by their name. For example, `find -name passwords.txt`                                                                                                                                                           |
| `grep`   | searches _inside_ for text. For example, `grep "password123" passwords.txt`                                                                                                                                                       |
| `&`      | Runs the command, but does not wait for it to finish before you can do anything else. The command runs in the backgorund, and is helpful for commands that might take a while to complete, or ones that you want to keep running. |
| `&&`     | Runs both commands, but waits for the first command to finish first, before the next. Like a set of dominoes.                                                                                                                     |
| `>`      | Used to redirect output. We can take the output of a command and send it to a file. This operator will overwrite anything that exists in the file.                                                                                |
| `>>`     | This redirector does the same thing, but instead of overwriting, it will just add the output to the bottom of the file.                                                                                                           |
ssh - remote shell
ssh username@ip
password


ls -a -------> show hidden folder 

ls --help

man ls ---> manual

|   |   |   |
|---|---|---|
|touch|touch|Create file|
|mkdir|make directory|Create a folder|
|cp|copy|Copy a file or folder|
|mv|move|Move a file or folder|
|rm|remove|Remove a file or folder|
|file|file|Determine the type of a file|


rm -R directoryname


Permission 101

ls -l

Permissions  Links   Owner   Group   Size    Date                 Name
-rw-r--r--             1        user2       user2   14      May 5 2021   important
            ↑
         Hard link count

file formate 

|         |        |       |
| ------- | ------ | ----- |
| First 3 | Owner  | `rwx` |
| Next 3  | Group  | `rwx` |
| Last 3  | Others | `rwx` |

Each permission has a numeric value:

| Permission    | Value |
| ------------- | ----- |
| Read (`r`)    | 4     |
| Write (`w`)   | 2     |
| Execute (`x`) | 1     |

common directories

**/etc**

commonplace location to store system files that are used by your operating system.

sudoers file  permission to run sudo or a set of commands as the root user.

"**passwd**" and "**shadow**" files.

how your system stores the passwords for each user in encrypted formatting called sha512.


**/var**

This folder stores data that is frequently accessed or written by services or applications running on the system. For example, log files from running services and applications are written here (**/var/log**)

log opt tmp


/**root**

home for the "root"

**/tmp**

store data that accessed one or twice
Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.


**Downloading Files (Wget)**

`wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt`

**Transferring Files From Your Host - SCP (SSH)**

|                                                             |                 |
| ----------------------------------------------------------- | --------------- |
| **Variable**                                                | **Value**       |
| The IP address of the remote system                         | 192.168.1.30    |
| User on the remote system                                   | ubuntu          |
| Name of the file on the local system                        | important.txt   |
| Name that we wish to store the file as on the remote system | transferred.txt |

`scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt`

`scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt`

**Serving Files From Your Host - WEB**

python3 -m http.server


```shell-session
tryhackme@mymachine:~# wget http://10.48.188.206:8000/myfile
```



