
### Specify the Network Interface

`-i INTERFACE`.  which network to listen

`-i any`  all

`-i eth0`

`ip address show` (or merely `ip a s`) would list the available network interface

we see one network card, `ens5`


This can be achieved by saving to a file using `-w FILE`

`.pcap`  file extension


`-r FILE` read file

`-c COUNT`  count specific default you have to press ctrl c

Tcpdump will resolve IP addresses and print friendly domain names  use `-n`

	`80` being resolved to `http`, you can use the `-nn`

 sudo tcpdump -i ens5 -c 5 -n


`-v` to produce a slightly more verbose output.

`-v` to produce a slightly more verbose output.

|Command|Explanation|
|---|---|
|`tcpdump -i INTERFACE`|Captures packets on a specific network interface|
|`tcpdump -w FILE`|Writes captured packets to a file|
|`tcpdump -r FILE`|Reads captured packets from a file|
|`tcpdump -c COUNT`|Captures a specific number of packets|
|`tcpdump -n`|Don’t resolve IP addresses|
|`tcpdump -nn`|Don’t resolve IP addresses and don’t resolve protocol numbers|
|`tcpdump -v`|Verbose display; verbosity can be increased with `-vv` and `-vvv`|
`eth0` is the **name of a network interface** (network adapter) in Linux.

`tcpdump -i wlo1 -w data.pcap` captures packets by listening on the `wlo1`

`tcpdump -i any -nn`

