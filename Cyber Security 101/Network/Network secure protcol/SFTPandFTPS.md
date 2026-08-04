SSH File Transfer Protocol

`sftp username@hostname`

`get filename` and `put filename` to download and upload files


Remember FTP uses **two connections**.

Example:

```
Control
Client ----------> Server
        Port 21

Data
Client <---------> Server
```

When FTPS encrypts everything, the firewall cannot inspect the FTP commands that tell it which data port will be used.

As a result:

- Extra ports must often be opened.
- Firewall configuration becomes more complicated.


| Port    | Protocol                   |
| ------- | -------------------------- |
| **21**  | FTP                        |
| **22**  | SSH / SFTP                 |
| **23**  | **Telnet**                 |
| **25**  | SMTP                       |
| **53**  | DNS                        |
| **80**  | HTTP                       |
| **110** | POP3                       |
| **143** | IMAP                       |
| **443** | HTTPS                      |
| **465** | SMTPS                      |
| **587** | SMTP Submission (STARTTLS) |
| **993** | IMAPS                      |
| **995** | POP3S                      |