
**Group Policy Objects (GPOs)**. GPOs are simply a collection of settings that can be applied to OUs.

GPOs can contain policies aimed at either users or computers, allowing you to set a baseline on specific machines and identities.

![](../assets/Pasted%20image%2020260801122514.png)

![](../assets/Pasted%20image%2020260801122643.png)


the `Default Domain Policy` and `RDP Policy` are linked to the `thm.local` domain as a whole, and the `Default Domain Controllers Policy` is linked to the `Domain Controllers` OU only. Something important to have in mind is that any GPO will apply to the linked OU and any sub-OUs under it. For example, the `Sales` will still be affected by the `Default Domain Policy`.

**Security Filtering** to GPOs so that they are only applied to specific users/computers under an OU. By default, they will apply to the **Authenticated Users** group, which includes all users/PCs.

![](../assets/Pasted%20image%2020260801123139.png)


![](../assets/Pasted%20image%2020260801123405.png)

![](../assets/Pasted%20image%2020260801123547.png)


![](../assets/Pasted%20image%2020260801123521.png)

`Computer Configurations -> Policies -> Windows Setting -> Security Settings -> Account Policies -> Password Policy` and change the required policy value:

GPO distribution

GPOs are distributed to the network via a network share called `SYSVOL`,

The SYSVOL share points by default to the `C:\Windows\SYSVOL\sysvol\` directory on each of the DCs in our network.

Once a change has been made to any GPOs, it might take up to 2 hours for computers to catch up. If you want to force any particular computer to sync its GPOs immediately, you can always run the following command on the desired computer:

```shell-session
PS C:\> gpupdate /force
```




we have been tasked with implementing some GPOs to allow us to:

1. Block non-IT users from accessing the Control Panel.
2. Make workstations and servers lock their screen automatically after 5 minutes of user inactivity to avoid people leaving their sessions exposed.



![](../assets/Pasted%20image%2020260801125006.png)

CREATE GROUP POILICY


![](../assets/Pasted%20image%2020260801124925.png)





![](../assets/Pasted%20image%2020260801124654.png)



![](../assets/Pasted%20image%2020260801125149.png)


**_Auto Lock Screen GPO_**

![](../assets/Pasted%20image%2020260801125541.png)

![](../assets/Pasted%20image%2020260801125646.png)

![](../assets/Pasted%20image%2020260801125826.png)


