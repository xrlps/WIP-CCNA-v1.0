
## Speed & Duplex
- Switch interfaces that support multiple speeds (10/100 and 10/100/1000 interfaces) will auto-negotiate what speed to use by default
- Speed, duplex mode, and description are configured on a per interface basis
- Ethernet devices must use the same standard on both ends of the link (a port configured to 100Mbps cannot work with a port configured to 10Mbps)
---
## Autonegotiation
- Switches default to a setting of duplex auto and speed auto
### IEEE Autonegotiation Protocol
- Allows the two UTP-based ethernet nodes on a link to negotiate so that they each choose to use the same speed and duplex settings
- Each node can state what it can do, and then each node picks the best options that both nodes support: the fastest speed and full duplex
- Configuring both speed (100) and duplex (full) commands disables IEEE autonegotiation
### IEE Autonegotiation Failures
When autonegotiation is disabled on one side, these default settings are applied:
- Speed: Devices use their slowest supported speed (often 10Mbps)
- Duplex: If the device speed is 10 or 100, use half duplex; otherwise use full duplex
### Cisco Autonegotiation Failures
Cisco switches override the IEEE autonegotiation protocol with the following:
- Speed: Sense the speed (without the use of autonegotiation), but if that fails, use the IEE default
- Duplex: Use the IEE defaults
---
## Locating Mismatches
### Duplex Mismatch
- If duplexes are mismatched on both sides of a switch, the switch will still be in an up/up connected state
- To identify duplex mismatches, check the duplex setting on each end of the link
- To identify duplex mismatches, watch for incrementing collision and late collision counters, shown via “show interfaces”
- The half-duplex interface will likely see the late collisions counter increment
### Speed Mismatch
- If speeds are mismatched on both sides of a switch, the switch will list the port in a down/down or notconnect state


