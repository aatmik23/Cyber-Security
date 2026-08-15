
These tasks range from simple encodings like xor  or **Base64** to complex operations like **AES encryption** or **RSA decryption**. CyberChef operates on **recipes**, a series of operations executed in order


https://gchq.github.io/CyberChef/


CyberChef consists of four areas. Each consists of different components or features.

These are the following areas:

1. Operations
2. Recipe
3. Input
4. Output

![](../../assets/Pasted%20image%2020260812110951.png)


## The Operations Area


|Operations|Description|Examples|
|---|---|---|
|From Morse Code|Translates Morse Code into (upper case) alphanumeric characters.|`- .... .-. . .- - ...` becomes `THREATS` when used with default parameters|
|URL Encode|Encodes problematic characters into percent-encoding, a format supported by URIs/URLs.|`https://tryhackme.com/r/room/cyberchefbasics` becomes `https%3A%2F%2Ftryhackme%2Ecom%2Fr%2Froom%2Fcyberchefbasics` when used with the parameter “Encode all special chars”|
|To Base64|This operation encodes raw data into an ASCII Base64 string.|`This is fun!` becomes `VGhpcyBpcyBmdW4h`|
|To Hex|Converts the input string to hexadecimal bytes separated by the specified delimiter.|`This Hex conversion is awesome!` becomes `54 68 69 73 20 48 65 78 20 63 6f 6e 76 65 72 73 69 6f 6e 20 69 73 20 61 77 65 73 6f 6d 65 21`|
|To Decimal|Converts the input data to an ordinal integer array.|`This Decimal conversion is awesome!` becomes `84 104 105 115 32 68 101 99 105 109 97 108 32 99 111 110 118 101 114 115 105 111 110 32 105 115 32 97 119 101 115 111 109 101 33`|
|ROT13|A simple Caesar substitution cipher which rotates alphabet characters by the specified amount (default 13).|`Digital Forensics and Incident Response` becomes `Qvtvgny Sberafvpf naq Vapvqrag Erfcbafr`|

## The Recipe Area


- `Save recipe`: This feature allows the user to save selected operations.
- `Load recipe`: Allows the user to load previously saved recipes.
- `Clear Recipe`: This feature will enable users to clear the chosen recipe during usage.

- `Open file as input`: This feature allows the user to upload a file as its input value.

![Open file as input option under the Input Area.](https://cdn-images.tryhackme.com/user-uploads/6645aa8c024f7893371eb7ac/room-content/6645aa8c024f7893371eb7ac-1728731934210.png)  

- `Clear input and output`: This feature allows the user to clear any input values inserted and the corresponding output value.
- `Reset pane layout`: This feature brings the tool's interface to its default window sizes.


