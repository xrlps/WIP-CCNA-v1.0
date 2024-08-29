- Created due to IPv4 address exhaustion (ran out of IPv4 addresses). Temporary solutions include NAT (sharing public globally unique IPv4 addresses for all host connections to the internet) and CIDR
- **128** bits in length; 32 hexadecimal digits (one hex digit per 4 bits)
- A 40-byte IPv6 header
- Does not use classful networks
- Allows for dual stack; routers forward both IPv4 and IPv6 packets
- On some links (WAN), routers do not need a global unicast address, for routing to work, instead they will use a generated link-local IPv6 address
- The routing process is almost exactly (if not exactly) the same as with IPv4 when it comes to encapsulation
#### IPv6 Protocols
1. RIPng (RIP next generation)
2. OSPFv3
3. EIGRPv6
4. MP BGP-4 (Multiprotocol BGP version 4)
5. ICMPv6
6. NDP (Replaces ARP to discover the MAC addresses used by neighbours in IPv6)
---
## Assigning Addresses to Hosts in a Subnet
- Statically (prefix length, default router, DNS)
- Dynamically (DHCP, SLAAC [a built-in IPv6 mechanism; Stateless Address Autoconfiguration])
---
## Abbreviating IPv6 Addresses
1. Remove leading 0s
2. Find any string of two or more consecutive “quartets” of all hex 0s and replace that set with a double colon “ :: “. This can only be done once, use the “ :: “ on the sequence of “quartets” with the most 0s
---
## IPv6 Prefix
- Prefix length is a mask concept, similar to an IPv4 subnet mask
- IPv6 prefix is the IPv6 equivalent of the subnet ID
#### Determining the Prefix
1. Copy the first “ / X” bits, change the rest of the bits to 0
2. If the prefix length is a multiple of 4, divide the prefix length by 4
3. Copy the hex digits determined to be in the prefix (per 2nd step)
---
## Modified EUI-64
- Using a modified EUI-64 (extended unique identifier); using an interfaces MAC address for the host portion of an IPv6 address
- For the interfaces that do not have a MAC address (a serial link), the router uses the MAC of the lowest-numbered router interface
#### Creating a EUI-64
1. Split the 6 byte (12-hex digit) MAC address in two halves (6 hex digits each)
2. Insert FFFE in between the two, making the interface ID now have a total of 16 hex digits (64 bits)
3. Invert the seventh bit of the interface ID (located in the first byte)
#### U/L Bit
- Universal / Local bit
- The seventh bit of a MAC address
- When this bit is set to a value of 0, the address is a UAA (Universally Administered Address)
- When this bit is set to a value of 1, the address is a LAA (Locally Administered Address)