
## Netfilter

Netfilter is the framework inside the with core functionalities, including packet filtering, NAT, and connection tracking.

**Iptables**

It uses the Netfilter framework that provides various functionalities to control network traffic.

**nftables**

successor to the “iptables” utility, with enhanced packet filtering and NAT capabilities. It is also based on the Netfilter framework.

**firewalld**

It works differently from the others and comes with different pre-built network zone configurations.


## ufw

uncomilicated firewall

eliminates the complications of making rules in a complex syntax in “iptables”(

beginner friendly

```shell-session
user@ubuntu:~$ sudo ufw status
Status: inactive
```

```shell-session
user@ubuntu:~$ sudo ufw enable
Firewall is active and enabled on system startup
```



```shell-session
user@ubuntu:~$ sudo ufw default allow outgoing
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)
```


The `default` in the command means that we are defining this policy as a default policy allowing all the outgoing traffic unless we define an outgoing traffic restriction on any specific application in a separate rule

![](../../assets/Pasted%20image%2020260811003710.png)


![](../../assets/Pasted%20image%2020260811003939.png)


![](../../assets/Pasted%20image%2020260811004057.png)




ufw default deny outgoing 


![](../../assets/Pasted%20image%2020260811154252.png)


![](../../assets/Pasted%20image%2020260811154555.png)


![](../../assets/Pasted%20image%2020260811154959.png)


![](../../assets/Pasted%20image%2020260811155508.png)

![](../../assets/Pasted%20image%2020260811155543.png)