## WLC Ports
- Physical connections made via an external wired or switched network
![[Pasted image 20240824001403.jpg]]
#### Service port
- Used for out-of-band management, system recovery, and initial boot functions
- Always connects to a switch port in access mode
- Can SSH, Telnet, or use HTTP(S) to connect to the controller
#### Distribution System port
- Used for all normal AP data
- Connects to a switch in 802.1Q trunk mode
- Can be configured with redundant pairs
- Can be configured to operate as a single logical group; a static link aggregation group (LAG) load balances traffic across individual ports. LAG offers resiliency, if one individual port fails, traffic will be redirected to the remaining working ports
#### Console Port
- Used for out-of-band management, system recovery, initial boot functions (asynchronous connections to a terminal emulator)
#### Redundancy port
- Used to connect to a peer controller for high availability (HA) operation
---
## WLC Interfaces
- Logical connections
- Made internally within the controller
- Must be configured with an IP address, subnet mask, default gateway, and a DHCP server
- Each interface is assigned to a physical port and VLAN ID
#### Management interface
- Used for normal management traffic (RADIUS authentication, WLC-to-WLC communication, web-based and SSH sessions, SNMP, NTP, syslog, etc)
- Used to terminate CAPWAP tunnels between the controller and its APs
- Faces the switched network
#### Redundancy management
- The management IP address of a redundant WLC that is part of a high availability pair of controllers
- The active WLC uses the management interface address, while the standby WLC uses the redundancy management address
#### Virtual interface
- IP address facing wireless clients when the controller is relaying client DHCP requests, performing client web authentications, and supporting client mobility
- Usually an RFC-1918 address
- Every controller in the same mobility group should have the same virtual address
#### Service port interface
- Bound to the service port and used for out-of-band management
#### Dynamic interface
- Used to connect a VLAN to a WLAN
---
## Configuring a WLAN
- Controller binds the WLAN to one of its interfaces and pushes the WLAN configuration out to all of its APs
- Each AP will advertise the WLAN by sending beacons, to which clients can probe and join the BSS
- Beacons are sent every 100ms (10 per second)
- Cisco controller support a maximum of 512 WLANs, but only 16 can be configured on an AP
**Before setting up a WLAN, the following needs to be configured**
1. SSID string
2. Controller interface and VLAN number
3. Type of wireless security