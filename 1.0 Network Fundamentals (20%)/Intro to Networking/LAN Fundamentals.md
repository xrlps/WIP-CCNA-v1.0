## LAN Types
#### Ethernet LAN
- Uses cables for links between nodes
- Uses routers, switches, and hubs
- A combination of user devices, LAN switches, and different types of cabling
![[Pasted image 20240824004834.png]]
#### Wireless LAN (WLAN)
- Uses radio waves for links between nodes
- Uses an access point (AP), which operates like an ethernet switch, in that all the wireless LAN nodes communicate with the wireless AP
---
## Ethernet (802.3):
- Refers to an entire family of standards that define how to send data over a particular type of cabling at a particular speed
- A protocol used for data-link in LANs
- A family of standards defined by IEEE
#### Variants of the Ethernet Data Link Protocol:
| Common Name:        | Speed:    | Informal IEE Standard Name: | Formal IEE Standard Name: | Cable Type, maximum length |
| ------------------- | --------- | --------------------------- | ------------------------- | -------------------------- |
| Ethernet 10         | 10 Mbps   | 10BASE-T                    | 802.3                     | Copper, 100m               |
| Fast Ethernet       | 100 Mbps  | 100BASE-T                   | 802.3u                    | Copper, 100m               |
| Gigabit Ethernet    | 1000 Mbps | 1000BASE-LX                 | 802.3z                    | Fiber, 5000m               |
| Gigabit Ethernet    | 1000 Mbps | 1000BASE-T                  | 802.3ab                   | Copper, 10m                |
| 10 Gigabit Ethernet | 10 Gbps   | 10GBASE-T                   | 802.3an                   | Copper, 100m               

---
## Ethernet Devices

#### Switch
- Forwards data based on a destination MAC address
- Layer 2 device
- Does the opposite receiving/transmitting of the NIC
- If two or more devices transmit a signal at the same time, the switch sends one frame and queues the other
- NIC **transmitters** use the pair connected to pins 1 and 2, NIC **receivers** use a pair of wires at pin positions 3 and 6
#### Hub
- Forwards data using physical standards, rather than data link standards
- Layer 1 device
- Repeats electrical signals out of all ports except the receiving port
- If two or more device transmit a signal, the signal collides
---
## MAC Address:
- 12 digit hexadecimal or 48 bit binary
- The layer 2 Ethernet address of a device
#### MAC Address Format
OU:IO:UI:VE:ND:OR
- OUI – Organizationally Unique Identifier – ID assigned to a particular manufacturer. Located in the first 3 bytes of the address
- VENDOR – Managed and assigned by the manufacturer