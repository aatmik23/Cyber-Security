
t is an email protocol used to **access and manage emails directly on the mail server**.

- **Default port:** `143` (unencrypted)
- **Secure version (IMAPS):** `993` (SSL/TLS)

           Phone
             │
             │
Laptop ─── Mail Server ─── Tablet
             │
             │
         Webmail


- Emails stay on the **mail server**.
- Every device sees the same mailbox.
- Reading, deleting, or moving an email on one device is synchronized to the others

pop s enough when working from one device,

quite convenient when you check your email via multiple clients.

pop3 which tends to minimize server storage as email is downloaded and deleted from the remote server,

- `LOGIN <username> <password>` authenticates the user
- `SELECT <mailbox>` selects the mailbox folder to work with
- `FETCH <mail_number> <data_item_name>` Example `fetch 3 body[]` to fetch message number 3, header and body.
- `MOVE <sequence_set> <mailbox>` moves the specified messages to another mailbox
- `COPY <sequence_set> <data_item_name>` copies the specified messages to another mailbox
- `LOGOUT` logs out

![](../../assets/Pasted%20image%2020260803223149.png)


![](../../assets/Pasted%20image%2020260803223252.png)

