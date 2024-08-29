## IPv6 Routes
- IPv6 is not enabled by default and must be enabled via the ***command here***
#### Connected & Local Routes
- Connected route: IPv6 address configured on the interface
- Local route: subnet of the IPv6 address configured on the interface (C)
- Connected and local routes are removed when the interface fails, and are added back when the interface/line protocol status goes up/up
- Routers do not create connected or local IPv6 routes for link-local addresses
#### Static Routes
1. **Directly Attached Static Routes**
- Specifies _only_ the outgoing interface (for the next hop)
- Cannot be used in Ethernet links
- Used over WAN links (point-to-point)
2. **Recursive Static Routes**
- Specifies _only_ the next hop router
- Used over WAN links (point-to-point)
- Used over Ethernet links
3. **Fully Specified Static Routes**
- Specifies _both_ the next hop router and the outgoing interface
- Used with link local IP addresses
- Used over WAN links (point-to-point)
- Used over Ethernet links
#### Static Default Routes
- ::/0 (same as 0.0.0.0/0)
- Administrative distance = 1
**Floating Static Route**
- Changing the administrative distance of a static default route to be used only when no other routes are found
---
## IOS Defaults for Administrative Distance
IOS Defaults for Administrative Distance

| Route Source         | Administrative Distance |
| -------------------- | ----------------------- |
| Connected routes     | 0                       |
| Static routes        | 1                       |
| NDP                  | 2                       |
| EIGRP                | 90                      |
| OSPF                 | 110                     |
| RIP                  | 120                     |
| Unknown/Unbelievable | 255                     |