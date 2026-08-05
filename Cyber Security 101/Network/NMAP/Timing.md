
running scan normal speed trigger IDS

Intrusion Detection System (IDS) is a system that detects unauthorised network and system intrusions. Examples include detecting unauthorised devices connected to the local network and unauthorised users accessing a system or modifying a file.


paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5)

`-T0` (or `-T 0`) or `-T paranoid` to opt for the slowest timing.


s. The number of parallel probes can be controlled with `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>`

minimum and maximum on the number of TCP and UDP port probes active simultaneously for a host group

- **1 probe** = One worker checking one door at a time.
- **100 probes** = 100 workers checking 100 doors simultaneously.


`--min-rate <number>` and `--max-rate <number>`. As the names indicate, they can control the minimum and maximum rates at which `nmap` sends packets


Nmap will limit itself to **500 packets per second**.


The total packet rate is about **1000 packets/sec** across all 10 hosts—not **1000 packets/sec per host**.


## `--host-timeout <time>`

This sets the **maximum amount of time Nmap will spend scanning one host**.

Example:

```
nmap --host-timeout 30s 192.168.1.10
```

If that host hasn't finished scanning within **30 seconds**, Nmap gives up on it and moves to the next host.


| Option                                                              | Explanation                                                                                        |
| ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `-T<0-5>`                                                           | Timing template – paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5) |
| `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>` | Minimum and maximum number of parallel probes                                                      |
| `--min-rate <number>` and `--max-rate <number>`                     | Minimum and maximum rate (packets/second)                                                          |
| `--host-timeout`                                                    | Maximum amount of time to wait for a target host                                                   |