## NDP
- Neighbour Discovery Protocol
- NDP is a part of ICMPv6
- Similar to ARP with additional functions, such as
1. Neighbor MAC Discovery
    - Used to let IPv6 LAN-based hosts to learn the MAC address of other hosts in the same subnet
    - Uses Request (NS) and Reply (NA) messages
2. Router Discovery
    - Hosts use RS messages to solicit RA messages from routers to learn about available IPv6 routes and other network configuration details.
    - Uses RS and RA messages
3. SLAAC
4. DAD
#### NDP Message Types (NS & NA)
###### NS
- Neighbor Solicitation
- ICMPv6 message type 135
- Asks the host of a particular IPv6 address to reply with an NA message that lists its MAC address
- Sent to the solicited-node multicast address associated with the target address (message is processed only by hosts whose last six hex digits match the address that is being queried)
###### NA
- Neighbour Advertisement
- ICMPv6 message type 136
- Lists the sender’s IPv6 and MAC address
- Sent as replies to an NS or as an unsolicited message (sent to the all-IPv6 hosts local-scope multicast address FF02::1)
#### NDP Message Types (RS & RA)
- Used to learn the identity of possible default gateways
###### RS
- Router Solicitation
- ICMPv6 message type 133
- Sent to FF02::2 (all IPv6 routers), to identify themselves
###### RA
- Router Advertisement
- ICMPv6 message type 134
- Lists important information including the link-local IPv6 address of the router
- Sent to the unicast address of the host that sent an RS or to FF02::1
---
## SLAAC
- Stateless Address Auto Configuration
- Used to dynamically learn and obtain IPv6 addresses without the use of DHCP servers
- Hosts use NDP messages to learn the subnet (prefix) used on the link and the prefix length
#### Process
1. The device sends a RS asking for the global unicast prefix, to the destination address FF02::2
2. The router responds with an RA, sent to the all nodes multicast address FF02::1
![[ipv6-stateless-address-autoconfiguration.gif]]
[Source](https://www.networkacademy.io/ccna/ipv6/stateless-address-autoconfiguration-slaac)

---
## DAD
- Duplicate Address Detection
- Used at the end of the SLAAC process and whenever a hosts interface initializes
- Uses NDP NS and NA messages
- A host sends an NS message to its own solicited node IPv6 address, if another host replies, it knows that the address is being used, otherwise it will use the address