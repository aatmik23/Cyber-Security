
![](../../assets/Pasted%20image%2020260817221118.png)


### HTTP Version

The **HTTP version** shows the protocol version used to communicate between the client and server. Here’s a quick rundown of the most common ones:

**HTTP/0.9** (1991)The first version, only supported GET requests.

**HTTP/1.0** (1996)Added headers and better support for different types of content, improving caching.

**HTTP/1.1** (1997)Brought persistent connections, chunked transfer encoding, and better caching. It’s still widely used today.

**HTTP/2** (2015)Introduced features like multiplexing, header compression, and prioritisation for faster performance.

**HTTP/3** (2022)Built on HTTP/2, but uses a new protocol (QUIC) for quicker and more secure connections.

Although HTTP/2 and HTTP/3 offer better speed and security, many systems still use **HTTP/1.1** because it’s well-supported and works with most existing setups. However, upgrading to HTTP/2 or HTTP/3 can provide significant performance and security improvements as more systems adopt them.



|   |   |   |
|---|---|---|
|**Request Header**|**Example**|**Description**|
|Host|`Host: tryhackme.com`|Specifies the name of the web server the request is for.|
|User-Agent|`User-Agent: Mozilla/5.0`|Shares information about the web browser the request is coming from.|
|Referer|`Referer: https://www.google.com/`|Indicates the URL from which the request came from.|
|Cookie|`Cookie: user_type=student; room=introtowebapplication; room_status=in_progress`|Information the web server previously asked the web browser to store is held in cookies.|
|Content-Type|`Content-Type: application/json`|Describes what type or format of data is in the request.|
