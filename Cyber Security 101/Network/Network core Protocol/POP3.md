It is an email protocol used to **download emails from a mail server to your local computer**.

- **Default port:** `110` (unencrypted)
- **Secure version (POP3S):** `995` (SSL/TLS)

- `USER <username>` identifies the user
- `PASS <password>` provides the user’s password
- `STAT` requests the number of messages and total size
- `LIST` lists all messages and their sizes
- `RETR <message_number>` retrieves the specified message
- `DELE <message_number>` marks a message for deletion
- `QUIT` ends the POP3 session applying changes, such as deletions


![](../../assets/Pasted%20image%2020260803222256.png)