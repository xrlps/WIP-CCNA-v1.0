## VRF [Virtual Routing & Forwarding]
- Used to divide a single router into multiple virtual routes. Similar to how VLANs are used to divide a single switch into multiple virtual switches
- Allows a router to build separate routing tables
    - Interfaces (Layer 3 only) and routes are configured to be in a specific VRF
- Traffic in one VRF cannot be forwarded out of an interface in another VRF
- Commonly used by service providers to allow one device to carry traffic from multiple customers, isolating each customers traffic from each other
![[Pasted image 20240823003752.png]]
