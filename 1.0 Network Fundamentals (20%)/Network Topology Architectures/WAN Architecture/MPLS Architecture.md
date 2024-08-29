## MultiProtocol Label Switching [MPLS]

- Uses a customer edge (CE) which is a customer router that connects to the MPLS
- Uses a provider edge (PE) which is a device that sits at the edge of the SP network, connecting to the CE
- Supports many Ethernet link standards
- The SP devices inside the MPLS network use an MPLS header when forwarding data across the MPLS network
- MPLS supports many connection types for a connection between CE to a PE; Ethernet (fiber), wireless, CATV, serial (leased line), etc
- Because many different customers connect to an MPLS domain, a MPLS VPN is used to differentiate traffic from different customers
- The only WAN service that can provide QoS
![[Pasted image 20240823003019.jpg]]
---
## MPLS VPN
- Used to create a private IP-based WAN for each of its customers, separating the routes learned from one customer to the other. The SP can support each customer while preventing packets from leaking from one customer to another
- Does not encrypt data, but keeps a private network by separating packets per customer through the use of an MPLS header
---
## MPLS Layer 3
- A layer 3 WAN service that routes IP packets between customer sites
- CE and PE routers peer using a routing protocol
- CE routers will learn the routes of adjacent CE routers from the relationship with the PE
- Advertises a customers routes to all other customer devices
- CE router becomes neighbours with the PE router it is directly connected to
- Customer routers at the customer edge (CE) add and remove an MPLS header as they enter and exit the MPLS network
- CE router does not become neighbours with other CE routers
- An access link connecting a CE to PE can use any routing protocol, where a link connecting PE to PE will have to use MPBGP
    - If the CE to PE connection uses any routing protocol other than MPBGP, route distribution mused be used
---
## MPLS Layer 2
- CE and PE routers do not form neighbour relationship
- The SP network is entirely transparent to CE routers; the SP functions like a large switch
- Adjacent CE routers will function as if they are directly connected
- Adjacent CE routers are in the same subnet