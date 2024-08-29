## 1. Autonomous AP Architecture
- An AP in this architecture is equipped with both wired and wireless hardware so that wireless client associations can be terminated onto a wired connection locally at the AP
- Connects SSIDs to wired VLANs through a trunk link connecting to an access layer switch
- The wireless side of an AP trunks 802.11 frames by marking them with the BSSID of the WLAN where they belong
- Data only travels through the AP to reach the network on the other side
- Adds a management VLAN so that the AP can use its management IP to trunk links that want to reach the AP
- Must be configured with a management IP address so that it can be remotely managed
- Can be connected to over SSH and Telnet to the CLI, or via HTTP and HTTPS over a browser session
- Logins require management users to log in (internal list of local usernames or AAA server like TACACS+ or RADIUS)
- The light-weight AP and the WLC bind together with a tunneling protocol, to carry 802.11-related messages and client data, using a protocol called CAPWAP
![[Pasted image 20240824000309.png]]
---
## 2. Cloud Based AP Architecture
- Instead of manually configuring every individual AP (via SSH, Telnet, HTTP/S, etc), you can push some changes to the cloud via Cisco Meraki, which automatically transmits instructions and collects information from APs
- Same physical topology as an autonomous architecture, but instead the APs are managed, controlled, and monitored centrally from the cloud
- The AP connects to clients via wireless, and sends traffic to the DS over a trunk link connected to an access layer switch
- Consists of two distinct planes (paths):
    1. Control plane: Traffic used to control, configure, manage, and monitor the AP itself
    2. Data plane: End-user traffic passing through the AP
![[Pasted image 20240824000339.jpg]]
---
## 3. Split-MAC (Lightweight) Architecture
- Separates the layer 2 and layer 3 functions of an AP
- AP hardware function is known as light-weight access point (LAP), and it performs only the real-time (client data) 802.11 operation
- Management functions are performed on a wireless LAN controller (WLC), which the light-weight AP is dependent on (cannot operate without the WLC)
- With the split-MAC architecture, multiple APs can be configured using a single device (WLC)
- The AP and WLC do not have to be on the same VLAN or IP subnet to function
- CAPWAP encapsulates the data between the LAP and WLC within new IP packets. The tunnel data can then be switched or routed across the campus network
- The LAP and WLC must authenticate with digital certificates (X.509 by default) to prevent an unauthorized AP being added to a network
- Does not use trunk links because all of the VLANs it supports are encapsulated and tunneled as L3 IP packets (rather than L2 VLANs)
- The AP is connected to a switch via an access link. A switch (or multiple switches) connect to the WLC via trunk link. When sending client traffic from an AP to the WLC, the AP sends it to the WLC over a CAPWAP tunnel (via management VLAN), which is actually an access link connected to a switch
![[Pasted image 20240824000403.jpg]]