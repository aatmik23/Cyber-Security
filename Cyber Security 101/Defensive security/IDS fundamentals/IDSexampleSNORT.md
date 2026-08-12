
uses signature-based and anomaly-based detections to identify known threats

However, you can configure Snort to detect specific types of network traffic not covered by the default rule files.

## Modes of Snort

![](../../assets/Pasted%20image%2020260811234020.png)



| Mode               | Description                                                                                    | Use Case                                  |
| ------------------ | ---------------------------------------------------------------------------------------------- | ----------------------------------------- |
| **Packet Sniffer** | Captures and displays packets without analyzing them.                                          | Network troubleshooting and monitoring.   |
| **Packet Logging** | Captures network traffic and saves it as **PCAP** for later analysis.                          | Forensics and investigating past attacks. |
| **NIDS**           | Monitors traffic in real time and uses rules/signatures to detect threats and generate alerts. | Real-time threat detection.               |