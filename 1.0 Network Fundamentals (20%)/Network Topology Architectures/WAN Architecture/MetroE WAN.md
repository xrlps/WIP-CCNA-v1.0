## Ethernet Line Service / E-Line (Point-to-Point)
- A customer router connects to a switch through an access link, which is connected to a MetroE Ethernet Virtual Circuit (EVC), which connects to a customer on the other end (again, with an access switch)
    - Routers use physical Ethernet interfaces
    - Routers on both ends of the EVC are in the same subnet
    - Routers on both ends of the EVC are neighbours and exchange routes
- A customer on one end of the EVC can directly communicate with one on the other end of the link only if they have a connecting E-Line
- E-Line services on a single access link use 802.1Q trunking, with a different VLAN ID (therefore different IP) for each E-Line service
- A device on one end can only communicate to the device on the other end (of the E-Line)
![[Pasted image 20240823002830.png]]
![[Pasted image 20240823002843.png]]
---
## Ethernet LAN Service / E-LAN [Full Mesh]
- All devices connected on the MetroE can send frames directly to one another, as if the customer edge routers are all connected to a switch (which is the E-LAN service)
- Called full mesh because there is a direct communication path for each set of devices, just like a LAN
- Devices are all in the same subnet
- A device on one end of the MetroE can communicate to all devices on the MetroE
![[Full-Mesh.webp]]
---
## Ethernet Tree Service / E-Tree (Hub and Spoke)
- A WAN topology in which the central site device can send frames directly to each remote (leaf) site, but the leaf sites can only send to the central site (not each other)
- The central site can communicate (and help facilitate communication) with all devices on the MetroE, but none of the devices on the MetroE can directly communicate with each other!
![[1__USh4nvBi4XCg3cj8HE9xQ 1.webp]]
