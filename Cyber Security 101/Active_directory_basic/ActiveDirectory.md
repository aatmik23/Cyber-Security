**Active Directory Domain Service ( DS)**. This service acts as a catalogue that holds the information of all of the "objects" that exist on your network

Users are one of the objects known as **security principal**

Users can be used to represent two types of entities:

- **People:** users will generally represent persons in your organisation that need to access the network, like employees.
- **Services:** you can also define users to be used by services like or MSSQL. Every single service requires a user to run, but service users are different from regular users as they will only have the privileges needed to run their specific service.


**_Machines_**

Machines are also considered "security principals" and are assigned an account just as any regular user. This account has somewhat limited rights within the domain itself.

The machine account name is the computer's name followed by a dollar sign. For example, a machine named `DC01` will have a machine account called `DC01$`.

**_Security Groups_**
groups to assign access rights to files or other resources to entire groups instead of single users. This

Security groups are also considered security principals and, therefore, can have privileges over resources on the network.

|                    |                                                                                                                                                           |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security Group** | **Description**                                                                                                                                           |
| Domain Admins      | Users of this group have administrative privileges over the entire domain. By default, they can administer any computer on the domain, including the DCs. |
| Server Operators   | Users in this group can administer Domain Controllers. They cannot change any administrative group memberships.                                           |
| Backup Operators   | Users in this group are allowed to access any file, ignoring their permissions. They are used to perform backups of data on computers.                    |
| Account Operators  | Users in this group can create or modify other accounts in the domain.                                                                                    |
| Domain Users       | Includes all existing user accounts in the domain.                                                                                                        |
| Domain Computers   | Includes all existing computers in the domain.                                                                                                            |
| Domain Controllers | Includes all existing DCs on the domain.                                                                                                                  |
Originational Units make it easier to manage large organizations.

An OU is a **special container** designed for administration.

**Advantages:**

- ✅ Can contain users, computers, groups, and even other OUs.
- ✅ Can have Group Policies (GPOs) applied.
- ✅ Can delegate administrative control.

For example, if the IT department has 50 computers, you can apply settings to **all IT computers at once** instead of configuring each one individually.
Windows Domain
        │
        ▼
Domain Controller (Server)
        │
        ▼
Active Directory
        │
        ├── OU: HR
        │      ├── Users
        │      └── Computers
        │
        ├── OU: IT
        │      ├── Users
        │      └── Computers
        │
        └── OU: Sales
               ├── Users
               └── Computers

![](../assets/Pasted%20image%2020260731221639.png)

container default created 

- **Builtin:** Contains default groups available to any Windows host.
- **Computers:** Any machine joining the network will be put here by default. You can move them if needed.
- **Domain Controllers:** Default that contains the DCs in your network.
- **Users:** Default users and groups that apply to a domain-wide context.
- **Managed Service Accounts:** Holds accounts used by services in your Windows domain.


![](../assets/Pasted%20image%2020260731222850.png)

