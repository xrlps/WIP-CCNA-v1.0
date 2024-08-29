
## Campus LAN
- A LAN that supports the end-user population. End-user devices connect to LAN switches, which in turn connect to the other switches such that a path exists
- Servers in this LAN are connected to switches, in a closed room called a data center, which connections to the campus LAN to support traffic to/from the users
---
## Overview of Switching Logic
- The role of a LAN switch is to forward ethernet frames to the correct destination MAC address. To achieve this goal, switches use logic: based on the source and destination MAC address in each frame’s ethernet header
- LAN switches forward ethernet frames inside a VLAN. If a frame enters via a port in VLAN 1, then the switch will forward or flood that frame out other ports in VLAN 1 only, and not out any other ports inside another VLAN
---
## How Switches Make Switching Decisions
***Primary job of the switch**
1.  Deciding when to forward a frame or when to filter (not forward) a frame, based on the destination MAC address    
***Overhead/Secondary jobs of the switch**
2. Preparing to forward frames by learning MAC address by examining the source MAC address of each frame received by the switch
***Overhead/Secondary jobs of the switch**
3. Preparing to forward only one copy of the frame to the destination by creating a (layer 2) loop free environment with other switches by using Spanning Tree Protocol (STP)
---
## Forwarding Known Unicast Frames
- To decide whether to forward a frame, a switch uses a dynamically built table (a MAC address table) that lists MAC addresses and outgoing interfaces
- Switches compare the frame’s destination MAC address to their MAC address table to decide whether the switch should forward a frame or ignore it
- Each switch makes an independent forwarding decisions based on its own MAC address table. Together, switches forward a frame so that it eventually reaches its destination
- The frames that consist of a known MAC address are referred to as known unicast frames or known unicast, simply because the destination MAC address is known
---
## Switch Learning: How Switches Build their MAC Address Table
- Switches build the address table by listening to incoming frames and examining the source MAC address in the frame. If a frame enters the switch and the source MAC address is not in the MAC address table, the switch creates an entry of the MAC address and the port that the MAC address came from
---
## Flooding Unknown Unicast and Broadcast Frames
- When there is no matching entry in the table, switches forward the frame out of all interfaces (except the incoming interface) using a process called **flooding**. The frame whose destination address is unknown is called an unknown unicast frame or unknown unicast. If the switch does not know where to send the frame it will send it to everyone but the sender.
- Switches also flood LAN broadcast frames (frames destined to the ethernet broadcast address of FFFF.FFFF.FFFF)
---
## MAC Address Removals:
- Switches remove MAC address entries due to age, table filling, or from manual removals using a command
### MAC Address Aging
- Switches remove entries that have not been used for a defined number of seconds (default 300s)
- If a switch receives a frame from a pre-existing MAC address, it resets the timer
- The switch times out (removes) any entries whose timer reaches the pre-defined time
### MAC Address Old Entries
- Each switch removes the oldest table entries, even if they are younger than the aging time setting
- If the table fills, the MAC address table uses content-addressable memory (CAM), a physical memory that has a great table lookup capability
- Size of the table depends on the size of the CAM
- When a switch tries to add a new MAC table entry and the table is full, the switch times out the oldest MAC entry to make space
---
## Avoiding Loops using STP:
- The third feature of LAN switches is loop prevention, implemented by STP
- Without STP, flooded frames would loop forever if we are using redundant links
- STP blocks some ports from forwarding frames so that only one active path exists between any pair of LAN segments
- STP causes an interface to go in either a forwarding state or a blocking state
    - Forwarding: The interface can send and receive data frames
    - Blocking: The interface cannot forward or receive data frames
---
## ARP Table
- Contains a list of IP addresses, MAC addresses, and the outgoing port
- When forwarding a packet to a host on the same subnet, the router encapsulates the packet, with a destination MAC address as found in the ARP table
- An ARP table entry with “ - “ is the routers MAC address and has no time out
- Dynamically learned ARP table entries have a timeout of 240min