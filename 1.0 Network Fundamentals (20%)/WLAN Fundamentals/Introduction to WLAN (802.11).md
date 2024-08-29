## 802.11
- A standard that wireless devices must adhere to
- Uses Radio Frequency (RF) signals
- Operates in half-duplex
- Transmissions between stations use the same frequency or channel
- To achieve full-duplex, one station’s transmission would have to occur on one frequency while it receives over a different frequency
- Wireless devices have a unique MAC address to send wireless frames at L2 over the air
---
## Basic Service Set (BSS)
- A logical wireless service area that is closed to specific wireless devices. These devices must advertise their capabilities to an AP (the center of the BSS) and they must be granted permission to join the BSS by the AP
- The AP operates in infrastructure mode; it offers the services that are necessary to form the infrastructure of a wireless network
- The AP establishes its BSS over a single wireless channel. The AP and the members of the BSS must use the same channel to communicate properly
- Bounded by the area where the AP’s signal is usable
- Membership with the BSS is called an association
- Devices in the same area as the BSS can overhear transmissions (assuming they are not encrypted)
- A basic service set is limited by the area that an AP cell can cover
![[Pasted image 20240823235604.png]]
### Basic Service Set ID (BSSID) & Service Set Identifier (SSID)
- A BSSID is advertised by the AP so that devices can find and try to join the BSS (tied to the BSSID)
- The BSSID is based on the AP’s own radio MAC address
- An AP also advertises the wireless network with a Service Set Identifier (SSID) containing the logical name
### Process of Joining a BSS
1. Wireless device sends an association request to the AP. The AP either grants or denies the request
2. Once associated, the device becomes a client (an 802.11 station [STA]), of the BSS
3. All communications to and from the client pass through the AP. The AP is the middleman and transports all frames. A middleman is used to keep the BSS stable and under control
---
## Distribution System
- To allow devices inside the BSS to communicate with devices outside the BSS, an AP can (and almost always does) connect/uplink into an Ethernet network (because an AP has both wired and wireless capabilities)
- The upstream wired Ethernet is the distribution system (DS)
- AP maps a VLAN to an SSID (can map multiple VLANs to the appropriate SSID)
- The AP uses the 802.1Q tag to map the VLAN numbers to the appropriate SSID
- When an AP uses multiple SSIDs, it trunks VLANs over the air and over the same channel to wireless clients
- The AP appears as multiple logical APs (one per BSS) with a unique BSSID for each BSS (incrementing the last digit of the radios MAC address)
- Wireless clients can be distributed across many SSIDs but these clients share the same APs hardware and must be on the same channel
![[Pasted image 20240823235643.png]]
---
## Extended Service Set
- Used to cover more area than a single APs cell can cover; adding more APs to cover a greater geographical area
- Multiple APs are interconnected by a switched infrastructure, called an ESS (extended service set)
- Combines BSS’s to cover a greater area
- Each AP’s cell has its own unique BSSID, but cells in the same ESS share the same SSID
- Passing from one AP to another is called **roaming**
![[Pasted image 20240823235722.png]]
---
## Independent Basic Service Set (IBSS) | Adhoc Wireless
- Allowing two or more wireless devices to communicate directly with each other, with no other means of network connectivity
- Also called **ad hoc** wireless network, or an **independent basic service set (IBSS)**
- One device takes the lead and begins advertising a network name and the necessary radio parameters (like an AP), and any device can join (usually under 10 devices for performance)
![[Pasted image 20240823235810.png]]
---
## CSMA/CA
- Carrier Sense Multiple Access with Collision Avoidance
- Used in wireless networks to avoid collisions
- When using CSMA/CD, a device will wait for other devices to stop transmitting before it transmits data itself