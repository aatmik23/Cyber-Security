


## FILTERING BY IP

```shell-session
tcpdump host example.com -w http.pcap
```

IP

`src host IP` or `src host HOSTNAME`.

`dst host IP` or `dst host HOSTNAME`.

## FILTERING BY PORT

```shell-session
user@TryHackMe$ sudo tcpdump -i ens5 port 53 -n
```

`src port PORT_NUMBER` and `dst port PORT_NUMBER`


## FILTERIN BY PROTOCOLS

examples include: `ip`, `ip6`, `udp`, `tcp`, and `icmp`.

```shell-session
sudo tcpdump -i ens5 icmp -n
```

### Logical Operators

`and`  `tcpdump host 1.1.1.1 and tcp` captures `tcp` traffic with `host 1.1.1.1`.

`or`  `tcpdump udp or icmp`

`not`   `tcpdump not tcp`


| Command                                      | Explanation                                                           |
| -------------------------------------------- | --------------------------------------------------------------------- |
| `tcpdump host IP` or `tcpdump host HOSTNAME` | Filters packets by IP address or hostname                             |
| `tcpdump src host IP` or                     | Filters packets by a specific source host                             |
| `tcpdump dst host IP`                        | Filters packets by a specific destination host                        |
| `tcpdump port PORT_NUMBER`                   | Filters packets by port number                                        |
| `tcpdump src port PORT_NUMBER`               | Filters packets by the specified source port number                   |
| `tcpdump dst port PORT_NUMBER`               | Filters packets by the specified destination port number              |
| `tcpdump PROTOCOL`                           | Filters packets by protocol; examples include `ip`, `ip6`, and `icmp` |

can count the lines by piping the output via the `wc` command