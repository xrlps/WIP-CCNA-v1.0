- The split-MAC concept can be applied to several different network architectures
- The following section describes all possible deployment options for a WLC
---
## Unified/Centralized WLC Deployment
- Locate the WLC in a central location to maximize the number of APs joined to it
- Supports the most amount of users, since the placement of the LAPs has high coverage
- Traffic to and from wireless users travel over CAPWAP tunnels that reach into the center of the network, near the core
- A single unified WLC can support up to a maximum of **6000** APs
![[Pasted image 20240824000634.png]]
---
## Cloud-Based WLC Deployment
- Placing a WLC in a central position in the network, inside a private cloud
- The WLC exists as a virtual machine, with a single AP supporting a maximum of **3000** APs
![[Pasted image 20240824000657.png]]
---
## Embedded WLC Deployment
- The WLC is embedded into a switch
- Used in small campuses, with a single embedded WLC supporting a maximum of **200** APs
![[Pasted image 20240824000720.png]]
---
## Cisco Mobility Express WLC Deployment
- The WLC function is co-located within an AP
- The AP that hosts the WLC forms a CAPWAP tunnel with the WLC, along with the other APs
- A mobility express WLC supports a maximum of **100** APs
![[Mobility-Express-Wireless-LAN-Controller-Deployment.webp]]
---
## Summary of WLC Deployment Architectures

|Deployment Model|WLC Location (DC, Access, Central, AP)|APs Supported|Clients Supported|Typical Use|
|---|---|---|---|---|
|Unified|Central|6000|64,000|Large enterprise|
|Cloud|Data Center|3000|32,000|Private cloud|
|Embedded|Access|200|4000|Small campus|
|Mobility Express|Other|100|2000|Branch location|
|Autonomous|N/A|N/A|N/A|N/A|