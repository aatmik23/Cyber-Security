
Automated hash recognition tools such as [hashID (opens in new tab)](https://pypi.org/project/hashID/) exist but are unreliable for many formats

web application database, it’s more likely to be MD5 than NTLM (NT LAN Manager

hashes are stored in `/etc/shadow`, which is normally only readable by root. They used to be stored in `/etc/passwd`, which was readable by everyone.

`shadow` file contains the password information. Each line contains nine fields, separated by colons (`:`)

The first two fields are the login name and the encrypted password

`man 5 shadow`

sword field contains the hashed passphrase with four components: prefix (algorithm id), options (parameters), salt, and hash. It is saved in the format `$prefix$options$salt$hash`

`man 5 crypt`.


|Prefix|Algorithm|
|---|---|
|`$y$`|yescrypt is a scalable hashing scheme and is the default and recommended choice in new systems|
|`$gy$`|gost-yescrypt uses the GOST R 34.11-2012 hash function and the yescrypt hashing method|
|`$7$`|scrypt is a password-based key derivation function|
|`$2b$`, `$2y$`, `$2a$`, `$2x$`|bcrypt is a hash based on the Blowfish block cipher originally developed for OpenBSD but supported on a recent version of FreeBSD, NetBSD, Solaris 10 and newer, and several Linux distributions|
|`$6$`|sha512crypt is a hash based on SHA-2 with 512-bit output originally developed for GNU libc and commonly used on (older) systems|
|`$md5`|SunMD5 is a hash based on the algorithm originally developed for Solaris|
|`$1$`|md5crypt is a hash based on the MD5 algorithm originally developed for FreeBSD|


           `root@TryHackMe# sudo cat /etc/shadow | grep strategos strategos:$y$j9T$76UzfgEM5PnymhQ7TlJey1$/OOSg64dhfF.TigVPdzqiFang6uZA4QA1pzzegKdVm4:19965:0:99999:7:::`
        

The fields are separated by colons. The important ones are the username and the hash algorithm, salt, and hash value. The second field has the format `$prefix$options$salt$hash`.

In the example above, we have four parts separated by `$`:

- `y` indicates the hash algorithm used, **yescrypt**
- `j9T` is a parameter passed to the algorithm
- `76UzfgEM5PnymhQ7TlJey1` is the salt used
- `/OOSg64dhfF.TigVPdzqiFang6uZA4QA1pzzegKdVm4` is the hash value


### MS Windows Passwords


NTLM OR MD5 IDENTICAL MD4

	stored in SAM (Security Accounts Manager).


tools like mimikatz exist to circumvent MS Windows security. Notably, the hashes found there are split into NT hashes and LM hashes.

