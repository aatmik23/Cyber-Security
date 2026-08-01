**Windows domain** is a group of users and computers under the administration of a given business. The main idea behind a domain is to centralise the administration of common components of a Windows computer network in a single repository called **Active Directory (AD)**. The server that runs the Active Directory services is known as a **Domain Controller (DC)**.

                  Company Network (Domain)

                 +----------------------+
                 |  Domain Controller   |
                 |      (Server)        |
                 | Runs Active Directory|
                 +----------+-----------+
                            |
         -----------------------------------------
         |                 |                     |
      Computer 1       Computer 2          Computer 3
     (Joined)         (Joined)            (Joined)

Active Directory Database

Users
------
Alice
Bob
Charlie

Computers
---------
PC-01
PC-02
PC-03

Groups
------
HR
IT
Managers


- **Domain Controller (DC):** A server that runs Active Directory and manages the domain.
- **Active Directory (AD):** A centralized database and directory service that stores information about users, computers, groups, and security policies.
- **Windows Domain:** A collection of computers and users managed centrally by a Domain Controller.

- **Centralised identity management:** All users across the network can be configured from Active Directory with minimum effort.
- **Managing security policies:** You can configure security policies directly from Active Directory and apply them to users and computers across the network as needed.

