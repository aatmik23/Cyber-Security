
TELNET (Teletype Network) protocol is a network for remote terminal connection


On the target lab machine, different services are running. We will experiment with three of them:

- Echo server: This server echoes everything you send it. By default, it listens on port 7.
- Daytime server: This server listens on port 13 by default and replies with the current day and time.
- Web (HTTP) server: This server listens on TCP port 80 by default and serves web pages.

the echo and daytime servers are considered security risks and should not be run;

![](../../assets/Pasted%20image%2020260803135026.png)

`telnet ip portnumber`

press the `CTRL` + `]` keys simultaneously.


![](../../assets/Pasted%20image%2020260803135422.png)

`GET / HTTP/1.1` and identify the host where anything goes, such as `Host: telnet.thm`

### What is the `Host` header?

In HTTP/1.1, the `Host` header tells the web server **which website you want**.