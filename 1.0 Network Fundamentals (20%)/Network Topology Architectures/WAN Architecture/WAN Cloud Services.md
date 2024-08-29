## Internet
- Using the internet to connect to a public cloud
- Can setup a VPN to encrypt traffic sent to the cloud over the internet, but still no QoS
### Positives
- An enterprise can use public cloud without having to wait to setup a private WAN connection
- An enterprise can easily switch its workload from one cloud provider to another
- The enterprise users can be using the service from anywhere
### Negatives
- Does not provide QoS
- Less secure than a private WAN
- Moving internal applications to the public cloud increases the network traffic of an enterprise’s Internet links
- No WAN SLA (SLA: similar to QoS but an agreement between ISPs and enterprises)
---
## Private Cloud (On-Premise)
- Creates a service, inside a company, to internal customers, that meets the requirements of the NIST list
- The company owns the tools that create the cloud and employs the people who use its services
## Public Cloud (Cloud)
- A public cloud provider offers to services to many different companies
- Offer different networking options, like VPN and WAN connections
### Community Cloud
- A shared cloud environment used by multiple organizations with similar needs, allowing them to collaborate and benefit from cost savings and specialized services
---
## Virtual Private Network
- Allows for private connections to the internet, just like a Private WAN provides data to be sent privately from one customer to the other
- A VPN tunnel is created between two devices by encapsulating the original IP packet with a VPN header and a new IP header
- The original packet is encrypted before being encapsulated with the new header
- The firewall or router in the recipients LAN (located on the other side of the VPN tunnel) decrypts the packet and sends it to the recipient
- Guarantees the following
    - Confidentiality (Privacy): Man in the middle cannot read the data
    - Authentication: Verifying the sender of a VPN packet is legit
    - Data Integrity: The data was not changed in transit
    - Anti-replay: A man in the middle cannot copy and keep on retransmitting old data
### VPN Tunnel
- A device encrypts the entire IP packet, then adds a VPN and new IP header to that encrypted packet
- Tunnel refers to any protocol’s packet that is sent by encapsulating the packet inside another packet
---
## Site-to-Site VPN
- Provides a service to many devices to access an external site
- Typically uses IPsec
- Used to permanently connect two sites over the internet
- A VPN between two devices that connect to each other over the internet
- The default gateway (or a firewall) will encrypt the packet and add a VPN header (create the tunnel)
- In a site-to-site VPN, a tunnel is formed only between two tunnel endpoints (ie, two routers connected to the internet)
![[Pasted image 20240823003302.png]]
---
## Site-to-Site IPsec [IP Security]
- IPsec defines a set of rules for creating secure VPNs (IP security)
- IPsec uses a pair of encryption algorithms to encrypt and decrypt data, using an encryption/session/shared key
- Anything sent over a GRE IPsec tunnel is encrypted
- Only supports unicast traffic; routing protocols like OSPF cannot be used
### GRE [Generic Routing Encapsulation]
- Creates tunnels like IPsec, without encrypting the original packet
- Can encapsulate a wide variety of Layer 3 protocols, broadcast, and multicast messages
- GRE over IPsec is used to get the flexibility of GRE with the security of IPsec
- The original packet is encapsulated with a GRE header and a new IP header, then this GRE packet is encrypted and encapsulated within an IPsec VPN header and new IP header
### DMVPN [Dynamic Multipoint VPN]
- A Cisco developed solution that allows routers to dynamically create a full mesh of IPsec tunnels without manually configuring every VPN tunnel
- A hub router must be set up with IPsec tunnels to each spoke router. The hub router will give all spoke routers information on how to dynamically form an IPsec tunnel to each other
---
## Remote-Access VPN
- Provides a service to one device to access an external site
- Used to allow end devices to access a company’s _internal_ resources _securely_ over the internet
- Used to provide on-demand access for end devices that want to securely access company resources, while connected to an insecure network
- Typically uses TLS
- End devices form secure tunnels to one of the company’s routers/firewalls acting as a TLS server. This allows the end users to securely access resources on the company’s internal network without being directly connected to the company network
### TLS [Transport Layer Security]
- Used in HTTPS (port 443)
- Formerly SSL [Secure Sockets Layer]
- A browser initiates a TCP connection to port 443, then initializes a TLS session. TLS encrypts data between the browser and the server and authenticates the user.
### VPN Client
- Uses TLS to secure (encrypts and new IP) all packets sent from a device, essentially a virtual private network
- Example: Cisco AnyConnect Secure Mobility Client
---
## Intercloud Exchange
- A company creates a private network as a service, connecting an enterprise to a large number of cloud providers
### Positives
- The customer is connected over a private WAN
- It is easy for the customer to change cloud providers
### Negatives
- An added third party
![[Pasted image 20240823003401.jpg]]