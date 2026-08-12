- **Source address:** The machine’s IP address that would originate the traffic.
- **Destination address:** The machine’s IP address that would receive the data.
- **Port:** The port number for the traffic.
- **Protocol:** The protocol that would be used during the communication.
- **Action:** This defines the action that would be taken upon identifying any traffic of this particular nature.
- **Direction:** This field defines the rule’s applicability to incoming or outgoing traffic.

### Types of Actions

##### Allow

| Action | Source         | Destination | Protocol | Port | Direction |
| ------ | -------------- | ----------- | -------- | ---- | --------- |
| Allow  | 192.168.1.0/24 | Any         | tcp      | 80   | Outbound  |
##### Deny

| Action | Source | Destination    | Protocol | Port | Direction |
| ------ | ------ | -------------- | -------- | ---- | --------- |
| Deny   | Any    | 192.168.1.0/24 | tcp      | 22   | Inbound   |

##### Forward

| Action  | Source | Destination | Protocol | Port | Direction |
| ------- | ------ | ----------- | -------- | ---- | --------- |
| Forward | Any    | 192.168.1.8 | tcp      | 80   | Inbound   |

### Directionality of Rules

##### Inbound Rules

applied to incoming traffic

http port 80 wev server traffic

## outbound Rules

outgoing smtp traffic

### forword rule

forword incoming traffic to web server

