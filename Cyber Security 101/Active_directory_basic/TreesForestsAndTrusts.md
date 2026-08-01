
Trees

`thm.local` domain was split into two subdomains for UK and US branches, you could build a tree with a root domain of `thm.local` and two subdomains called `uk.thm.local` and `us.thm.loca`

![](../assets/Pasted%20image%2020260801204018.png)
 
 
 IT people from the UK will have their own DC
 policies can also be configured independently for each domain in the tree.

. The **Enterprise Admins** group will grant a user administrative privileges over all of an enterprise's domains.

Forests

The union of several trees with different namespaces into the same network is known as a **forest**

suppose we aquare another company thm and mht
we use forest

Trust Relationships

THM UK might need to access a shared file in one of MHT ASIA servers. For this to happen, domains arranged in trees and forests are joined together by **trust relationships**.

relationship that can be established is a **one-way trust relationship**. In a one-way trust, if `Domain AAA` trusts `Domain BBB`, this means that a user on BBB can be authorised to access resources on AAA:

![](../assets/Pasted%20image%2020260801204537.png)


**Two-way trust relationships** can also be made to allow both domains to mutually authorise users from the other. By default, joining several domains under a tree or a forest will form a two-way trust relationship.

domains doesn't automatically grant access to all resources on other domains.

