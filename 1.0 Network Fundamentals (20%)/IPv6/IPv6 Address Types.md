## Link-Local Addresses (FE)
- Not used for normal IPv6 packet flows that contain data for applications
- Used by overhead protocols (ex, NDP) and for routing
- When configuring a link-local IPv6 address as the next hop address, the outgoing interface must be specified in the command too (**fully specified**)
- Used as the next-hop IP address in IPv6 routes (hosts refer to the router’s link-local address as the default gateway)
- Does not forward packets to other subnets
- Begins with the prefix FE80:://10, FE9, FEA, FEB
- IOS creates a link-local address for any interface that has configured at least one other unicast address (automatically generated)
#### Link-local Scope
- Routers do not forward packets sent to an address in this scope
---
## IPv6 Multicast Address (FF)
#### General Multicast Address
- Begins with FF3/12
- Higher value of the fourth hex digit means the packet has greater scope
- Instead of using L3 and L2 broadcasts, IPv6 uses L3 multicast addresses, which cause Ethernet frames to use Ethernet multicast addresses, as a result
    - All the hosts that should receive the message receive it
    - Hosts that do not need to process the message can make that choice with much less processing as compared to IPv4
#### Link-local Multicast Address
- An IPv6 address that begins with FF02
- Packets sent to a multicast address with a link-local scope stay on the local link (local subnet)
- A reserved multicast address to which devices apply a link-local scope
#### Solicited-Node Multicast Address
- Used in NDP as the address for retrieving a MAC address, like ARP uses FFF.FFF.FFF
- Begins with FF02::1:FF:
- Ends with the last 6 hex digits of the unicast IPv6 address
- A host or router calculates a matching solicited node multicast address for every unicast address on an interface (ie a solicited node multicast address for a link local address, unique local address, global address, etc)
#### IPv6 Local-Scope Multicast Addresses
| Name              | Multicast Address | Meaning                                                       | IPv4 Equivalent |
| ----------------- | ----------------- | ------------------------------------------------------------- | --------------- |
| All-nodes         | FF02::1           | All nodes (all interfaces that use IPv6 that are on the link) | 224.0.0.1       |
| All-routers       | FF02::2           | All-routers (all IPv6 router interfaces on the link)          | 224.0.0.2       |
| All OSPF          | FF02::5           | All OSPF routers                                              | 224.0.0.5       |
| All OSPF-DR       | FF02::6           | All OSPF DR routers                                           | 224.0.0.6       |
| RIPng Routers     | FF02::9           | All RIPng routers                                             | 224.0.0.9       |
| EIGRPv6 Routers   | FF02::A           | All routers using EIGRP for IPv6                              | 224.0.0.10      |
| DHCP Relay Agents | FF02::1:2         | All routers acting as a DHCPv6 relay agent                    | n/a             

#### IPv6 Multicast Scope
| Scope Name           | First “Quartet” | Scope Defined by         | Meaning                                                                                                                         |
| -------------------- | --------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| Interface-Local      | FF01            | Derived by device        | Packet remains within the device. Used for internally sending packets to services running on the same host                      |
| Link-Local           | FF02            | Derived by device        | Host that creates the packet can send it onto the link, but no routers forward this packet                                      |
| Site-Local           | FF05            | Configurated on a router | Intended to be more than link-local (routers forward) but less than organizational local (limit packets to not cross WAN links) |
| Organizational-Local | FF08            | Configurated on a router | Broad, (for an entire company or organization)                                                                                  |
| Global               | FF0E            | No boundary              | No boundary                                                                                                                     |

---
## Loopback Address
- ::1
- Packets sent to ::1 do not leave the host and are delivered down the stack to IPv6 and back up the stack to the application on the local host

---
## Unknown IPv6 Address
- ::
- Used when a host does not know its own IPv6 address and needs to dynamically discover it
---
## Global Unicast (2000::/3) Address
- IP addresses that are publicly routable to/from the internet
- Typically begins with 2 or 3, but can use all prefixes that aren’t used by other address types
- Global ID (48 bits) + Subnet ID (16 bits) + Interface ID (48 bits)
---
## Anycast Address (2000::/3)
- Assigned from the global unicast address space (2000::/3)
- Routers collectively implementing a service send one packet to an IPv6 address, and the routers forward this packet to the nearest router that supports that service
- Looks like a regular unicast address, but has the keyword **ipv6 address anycast**
- All anycast addresses in each subnet has the same prefix value and all binary 0s for the interface ID
#### Process
1. Two routers configure the exact same IPv6 address (anycast address)
2. When any router receives a packet for that address, the other routers route the packet to the nearest router that supports this address
---
## Unique Local Address (FD)
- Like an RFC 1918 address
- A private address only routable within a subnet
- FD (8 bits) + Global ID (40 bits) + Subnet ID (16 bits) + Interface ID (48 bits)
---
## Types of IPv6 Addresses
| Address Type   | First Hex Digit                                 |
| -------------- | ----------------------------------------------- |
| Global Unicast | 2 or 3 (originally); all not otherwise reserved |
| Unique Local   | FD                                              |
| Multicast      | FF                                              |
| Link Local     | FE80                                            

---
## Unicast IPv6 Addresses Cause a Router To
- Give the interface a unicast IPv6 address
- Enable the routing of IPv6 packets in/out that interface
- Define the IPv6 prefix (subnet) that exists off that interface
- Tell the router to add a connected IPv6 route for that prefix, to the IPv6 routing table, when that interface is up/up