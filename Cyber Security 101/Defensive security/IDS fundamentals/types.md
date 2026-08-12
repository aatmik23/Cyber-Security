
classified on the basis of deployment and detection mode

### Deployment mode

**Host Intrusion Detection System** HIDS

installed on the host computer detect threat with that particular host

hard to manage on large network

**Network Intrusion Detection System** NIDS

malicious activity within the whole network

They monitor the network traffic of all the hosts involved to detect suspicious activities. It provides a centralized view of all the detections inside the whole network.

![](../../assets/Pasted%20image%2020260811231601.png)



### Detection Based IDS

#### Signature Based IDS 

Each attack has its unique pattern, which is known as a signature.

this store in database happen again in future alert secuirty administrator

not detect zero day attack

#### Anomly based IDS

detect normal behavior detect any deviation from normal behaviour

can also detect zero day attack

genertae many false positive but can be fine tunned

#### Hybrid based IDS

use both

