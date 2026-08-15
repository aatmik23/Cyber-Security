**INetSim: Internet Services Simulation Suite****!**

 10.49.151.136  
NetSim configuration by running this command `sudo nano /etc/inetsim/inetsim.conf` and look for the value `#dns_default_ip 0.0.0.0`.

![](../../assets/Pasted%20image%2020260813112146.png)

remove # and make dns_default_ip to your ip

Confirm that the changes have been successful by checking the value of `dns_default_ip` using this command `cat /etc/inetsim/inetsim.conf | grep dns_default_i`


![](../../assets/Pasted%20image%2020260813112541.png)

![](../../assets/Pasted%20image%2020260813112735.png)


![](../../assets/Pasted%20image%2020260813113226.png)



connection report

This is usually saved in **/var/log/inetsim/report/** directory. You should be able to see something like this.

```terminal
Report written to '/var/log/inetsim/report/report.2594.txt' (14 lines)
=== INetSim main process stopped (PID 2594) ===
```


ead the file using this command `sudo cat /var/log/inetsim/report/report.2594.txt`. This may differ from your machine.


![](../../assets/Pasted%20image%2020260813114132.png)
