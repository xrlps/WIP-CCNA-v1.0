- The following are examples of technologies used to connect private enterprises together via a WAN
### Leased Line
- A dedicated physical link, typically connecting two sites
- Uses serial connections (PPP or HDLC encapsulation)
- Has a high cost, high installation time, and slower speeds compared to other Ethernet WAN technologies
### MPLS VPN
- MPLS networks use a _shared_ infrastructure; many different customer enterprises connect to and share the same infrastructure to make WAN connections
- The label switching refers to MPLS allowing VPNs to be created over MPLS through the use of labels. Labels are used to separate traffic from different customers. These labels are placed in between the layer 2 Ethernet header and the layer 3 IP header, which is why MPLS may be referred to as a layer 2.5 protocol
### Internet
- The internet can be used as a means to connect private enterprises together
- Less secure than a leased line or MPLS
---
## Metro Ethernet [MetroE]
- A layer 2 **service** that includes a variety of WAN services. Has the purpose of allowing LANs to connect to each other over great distances by connecting to a SP
- Uses Ethernet physical links to connect the customers devices to the server providers device
- The MetroE architecture functions as if customer devices (connected to their LAN) connect to a switch. The WAN provider forwards Ethernet frames from one customer device to another
- SP puts a device, typically an Ethernet switch, physically near to many customer sites in a SP facility called point of presence (PoP)
- The physical link between the customer and the SP is an access link*,* and everything that happens on this link falls within the definition of the user network interface (UNI [network is the SP’s network, User is the customer])
![[Pasted image 20240823002636.png]]
---
## Ethernet Standards Used in MetroE
![[Pasted image 20240823002652.jpg]]

|**Name**|**Speed**|**Distance**|
|---|---|---|
|100BASE-LX10|100 Mbps|10 Km|
|1000BASE-LX|1 Gps|5 Km|
|1000BASE-LX10|1 Gbps|10 Km|
|1000BASE-ZX|1 Gbps|100 Km|
|10GBASE-LR|10 Gbps|10 Km|
|10GBASE-ER|10 Gbps|40 Km|

---
## MetroE Service Types

|**MEF Service Name**|**MEF Short Name**|**Topology Terms**|**Description**|
|---|---|---|---|
|Ethernet Line Service|E-Line|Point-to-point|Two customer premise equipment devices (CPE) exchange Ethernet frames (like a leased line)|
|Ethernet LAN Service|E-LAN|Full mesh|Acts like a LAN, where all devices can send frames to one another|
|Ethernet Tree Service|E-Tree|Hub and spoke||
|Partial mesh||||
|Point-to-multipoint|A central site can communicate to remote sites, but remote sites cannot communicate directly with each other|||
