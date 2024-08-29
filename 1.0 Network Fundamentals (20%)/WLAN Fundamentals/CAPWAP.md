## Introduction to CAPWAP
- A tunneling protocol used to encapsulate data between a LAP and WLC within new IP packets
- Tunneled data is switched or routed across the campus network
#### Messages
1. **CAPWAP control messages:**
    - **UDP 5246** (Control tunnel)
    - Carries exchanges that are used to configure the AP and manage its operation
    - Authenticated and encrypted (prevent AP hijacking)
2. **CAPWAP data:**
    - **UDP 5247** (Data tunnel)
    - Used for packets traveling to and from wireless clients that are associated with the AP
    - Data packets are transported over the data tunnel (un-encrypted by default)
    - Optionally, uses Datagram Transport Layer Security (DTLS) to encrypt data for an AP
---
## CAPWAP Additional Functions
#### Dynamic channel assignment:
- WLC automatically chooses and configures the RF channel based on other active AP in the area
#### Transmit power optimization:
- WLC automatically sets the transmit power of each AP based on the coverage area needed
#### Self-healing wireless coverage:
- If an AP radio dies, the coverage hole can be “healed” by turning up the transmit power of other surrounding APs automatically
#### Flexible client roaming:
- Clients can roam between APs with very fast roaming times
#### Dynamic client load balancing:
- If two or more APs are positioned to cover the same area, the WLC can associate clients with the least used AP
#### RF monitoring
- WLC manages each AP so that it scans channels to monitor the RF usage
- By listening to a channel, the WLC can remotely gather information about RF interference, noise, signals from other APs, and signals from rogue APs, or ad hoc clients
#### Security management
- WLC can authenticate clients from a central service and can require wireless clients to obtain an IP address from a DHCP server, before associating them to the WLAN
#### Wireless intrusion protection system
- Leveraging its central location, the WLC can monitor client data to detect and prevent malicious activity