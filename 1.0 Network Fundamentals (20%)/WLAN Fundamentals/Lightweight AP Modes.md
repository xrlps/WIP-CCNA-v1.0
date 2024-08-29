- Below listed are different special purpose modes that a lightweight AP can operate in
---
## 1. Local
- The default lightweight mode, offering one or more functioning BSSs on a specific channel
- When it is not transmitting, the AP will scan the other channels to measure the level of noise, interference, rogue devices, and match against intrusion detection system (IDS) events
## 2. Monitor
- AP does not transmit, but the receiver is enabled to act as a dedicated sensor
- The AP checks for IDS events, detects rogue access points, and determines the position of stations through location-based services
## 3. Flex connect
- An AP at a remote site that can locally switch traffic between an SSID and VLAN if its CAPWAP tunnel to the WLC is down (and is configured to do so)
## 4. Sniffer
- Dedicates its radios to receiving 802.11 traffic from other sources (like a sniffer/packet capture device)
- Captured traffic is forwarded to a PC running a network analyzer like WireShark
## 5. Rogue detector
- Dedicates itself to detecting rogue devices by correlating MAC addresses heard on the wired network with those heard on the wireless network. Rogue devices appear on both networks
## 6. Bridge
- Becomes a dedicated bridge (point-to-point or point-to-multipoint) between two networks
- Two APs in bridge mode can be used to link two locations separated by distance
- Multiple APs in bridge mode can form an indoor or outdoor **mesh** network
## 7. Flex+Bridge
- Flex connect operation that is enabled on a mesh AP
## 8. SE-Connect
- Dedicates its radios to spectrum analysis on all wireless channels
- Can remotely connect to the AP with a PC to analyze data