
**PGP** stands for Pretty Good Privacy.

software that implements encryption for encrypting files, performing digital signing, and more. is an open-source implementation of the OpenPGP standard.

gpg is commonly used in email it used to sign email message integrity


**PGP** = Pretty Good Privacy  
**GPG** (`gpg`) = GNU Privacy Guard, a program that implements the OpenPGP standard.


                 GPG KEY
                    │
             ┌──────┴──────┐
             │             │
          Primary        Subkey
             │             │
           [SC]           [E]
             │             │
       Sign/Certify      Encrypt


You entered:

```
Real name: strategos
Email: strategos@tryhackme.thm
```

So GPG created:

```
Strategos <strategos@tryhackme.thm>
```

This is called a **User ID (UID)**.

It's basically information attached to the key to identify who the key is supposed to belong to.


- You would use `gpg --import backup.key` to import your key from backup.key
- To decrypt your messages, you need to issue `gpg --decrypt confidential_message.gpg`

