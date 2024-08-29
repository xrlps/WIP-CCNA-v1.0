- A networking device that forwards packets by connecting to various physical network links like:
    1. Ethernet LAN
    2. Ethernet WAN
    3. Serial WAN links
- Forwards packets layer 3 PDU to/from different networks (layer 3/IP routing)
- Use serial interfaces to connect to a serial link. Each point-to-point link can use HDLC (default) or PPP
- Have Telnet and SSH disabled by default (unlike switches)
- Have interfaces shutdown by default (unlike switches)
---
## CSU/DSU
- Channel service unit/data service unit
- Routers contain a physical component called a CSU/DSU
- Connects a leased line to a router
### External CSU/DSU
- Connects to the router’s serial card via serial cable
### Internal CSU/DSU
- A router serial port has an RJ-48 port which a service provider uses to connect to the CSU/DSU
---
## Router Installation
1. For Ethernet LAN interfaces, connect the RJ-45 port of both the router and switch together using a copper Ethernet cable
2. For a serial WAN port
    A. If using an external CSU/DSU , connect the router’s serial interface to the CSU/DSU and the CSU/DSU to the line from the telco
    B. If using an internal CSU/DSU, connect the router’s serial interface to the line from the telco
3. For any Ethernet WAN port
    A. Confirm the required Ethernet standard and SFP type required to connect to the link, and use that SFP
    B. Install the SFPs into the router and connect the Ethernet cable for the Ethernet WAN link to the SFP on each end of the link
---
## Router Interface Status Codes

|**Name**|**Location**|**Meaning**|
|---|---|---|
|Line status|First status code|Layer 1 status|
|Protocol status|Second status code|Layer 2 status|

---
## IP Routing
- The process of forwarding packets across TCP/IP networks
- When a router is de-encapsulating the data-link frame, leaving the IP packet, the destination IP address does **not** change
- Routes for remote subnets list an outgoing interface and a next hop-address
### Routing process of a Host
1. Check if the destination IP of the packet is in it’s local subnet, using its own IP address/mask to determine the range of addresses in the local subnet
2. If the destination is local, send directly:
    A. Find the destination host’s MAC address. Use ARP table entry or ARP.
    B. Encapsulate the IP packet in data-link frame, with the destination data-link address of the destination host
3. If the destination is not local, send to the default gateway
    A. Find the default gateway’s MAC address. Use ARP table entry or ARP
    B. Encapsulate the IP packet in a data-link frame, with the destination data-link address of the default-gateway
### Process of a Router
1. For each received data-link frame, choose whether or not to process the frame. Process the frame if:
    A. The frame has no errors (per the data-link FCS)
    B. The frame’s destination data-link address is the router’s address, a multicast address, or a broadcast address
2. If choosing to process the frame at step 1, de-encapsulate the packet from inside the data-link frame 
3. Make a routing decision. Compare the packet’s destination IP address to the routing table and find the route that matches the destination address. This route identifies the outgoing interface of the router (or the next hop)
4. Encapsulate the packet in a data-link frame appropriate for the outgoing interface. When forwarding out a LAN interface, use ARP to find the address of the device forwarding to
5. Transmit the frame out the outgoing interface, as listed in the matched IP route
---
## Routing Table
- A router contains a routing table that helps it make necessary decisions when forwarding IP packets
- A routing table consists of the following
    - Next-hop IP address
    - Subnet masks
    - Network masks
    - Exit interfaces