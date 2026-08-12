## logs everywhere

log sources are mainly divided into two categories

## 1) Host-Centric Log Sources

These log sources capture events that occurred within or related to the host. Devices that generate host-centric logs include Windows, linux, servers, etc. Some examples of host-centric logs are:

- A user accessing a file
- A user attempting to authenticate.
- A process execution activity
- A process adding/editing/deleting a registry key or value.
- powershelll execution

## 2) Network-Centric Log Sources

Network-related logs are generated when the hosts communicate with each other or access the internet to visit a website. Devices that generate network-centric logs are firewalls, ids/ips, routers, etc. Some examples of network-centric logs are:

- ssh connection
- A file being accessed via ftp
- Web traffic
- A user accessing the company's resources through .vpn
- Network file sharing Activity

Together, these host-centric and network-centric log sources constantly create numerous logs in a network.


### Problems with Logs

- **Numerous Log Sources:** Many devices generate huge numbers of logs, making investigation difficult.
    
- **No Centralization:** Logs are stored on different machines, so analysts must check each device separately.
    
- **Limited Context:** A single log may look harmless, but combining logs can reveal an attack.
    
- **Limited Analysis:** Too many logs make manual analysis difficult and easy to miss threats.
    
- **Format Issues:** Different devices generate logs in different formats, making analysis harder.
    

➡️ **Solution:** A centralized **SIEM** can collect, correlate, and analyze logs from multiple sources


