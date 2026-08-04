
File Transfer Protocol

- `USER` is used to input the username
- `PASS` is used to enter the password
- `RETR` (retrieve) is used to download a file from the FTP server to the client.
- `STOR` (store) is used to upload a file from the client to the FTP server.

server listens on TCP port 21 by default;


Since these are handled differently, FTP has two modes:

| Mode   | Used for                                      |
| ------ | --------------------------------------------- |
| ASCII  | Text files                                    |
| Binary | Images, videos, PDFs, ZIPs, executables, etc. |

ASCII mode is for **plain text files** such as:

- `.txt`
- `.html`
- `.css`
- `.js`
- `.c`
- `.py`

`get coffee.txt` allowed us to retrieve the file we want


![](../../assets/Pasted%20image%2020260803214554.png)


`get coffee.txt` allowed us to retrieve the file we want


![](../../assets/Pasted%20image%2020260803214940.png)


ls  ---- client send LIST

