
process 101

ps -- to check process

`ps aux`  To see the processes run by other users

`top` real-time statistics about the processes running on your system instead of a one-time view. These statistics will refresh every 10 seconds,


`kill 1337`

- SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
- SIGKILL - Kill the process - doesn't do any cleanup after the fact
- SIGSTOP - Stop/suspend a process

namespaces

**systemd**  first process that start on boot

`systemctl` -- this command allows us to interact with the **systemd** process/daemon.

`systemctl [option] [service]`

We can do five options with `systemctl`:

- Start
- Stop
- Enable
- Disable
- Status

**Introduction to Backgrounding and** **Foregrounding** **in Linux**

`Ctrl + Z`  background the process 
& use to backhround the process
echo is foreground

**Foregrounding a process**

`fg` to bring process to focus