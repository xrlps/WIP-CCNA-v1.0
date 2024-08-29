## Independent Basic Service Set
- AKA ad-hoc
- Used in airdrop
---
## Infrastructure Basic Service Set
- The use of an AP to connect devices in a network
- The AP connects to devices wirelessly and connects to a LAN through a wired connection
---
## Mesh Network
- Instead of running Ethernet cabling to every single AP, a mesh topology of multiple APs are used, with only one AP connected via Ethernet cabling
- APs relay client traffic to each other over wireless backhaul links, rather than wired Ethernet
- Bridging wireless traffic from AP to AP, in a daisy-chain fashion (using another wireless channel for AP to AP communication)
- Leverages dual radios (one AP using a channel in one range of frequency, and one AP in a different range)
- Client traffic is bridged from AP to AP over channels as a backhaul network
- At the edge of the mesh network, the backhaul traffic is bridged to the wired LAN Ethernet infrastructure
- APs in a mesh typically belong to the same ESS
- At least one AP is connected to the wired network, and it is called the RAP (Root Access Point)
- The other APs that are not an RAP are called MAPs (Mesh Access Point)
![[Pasted image 20240824000022.png]]