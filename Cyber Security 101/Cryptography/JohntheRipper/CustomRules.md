
Custom rules are defined in the `john.conf` file.

found in `/opt/john/john.conf`

- `Az`: Takes the word and appends it with the characters you define
- `A0`: Takes the word and prepends it with the characters you define
- `c`: Capitalises the character positionally

- `[0-9]`: Will include numbers 0-9  
    
- `[0]`: Will include only the number 0
- `[A-z]`: Will include both upper and lowercase  
    
- `[A-Z]`: Will include only uppercase letters
- `[a-z]`: Will include only lowercase lette

- `Az` → append something to the end
- `[0-9]` → the something can be any number from `0` to `9`

So John can generate:

password0

password1

password2

...

password9


`[!£$%@]`: Will include the symbols `!`, `£`, `$`, `%`, and `@`

_____________________________________________________


`[List.Rules:PoloPassword]`

`cAz"[0-9] [!£$%@]"`

Utilises the following:

- `c`: Capitalises the first letter
- `Az`: Appends to the end of the word
- `[0-9]`: A number in the range 0-9
- `[!£$%@]`: The password is followed by one of these symbols
___________________________

`--rule=PoloPassword` flag.

As a full command: `john --wordlist=[path to wordlist] --rule=PoloPassword [path to file]`

