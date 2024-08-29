## Open Authentication [~~Weak]~~
- One of the two authentication methods offered in the original 802.11 standard
- Offers open access to a WLAN
- The only point of authentication is that a client must use an 802.11 authentication request before it attempts to associate with an AP
- Typically used in public Wi-Fi’s, like at a coffee shop or hotel
- Client OS will likely flag such networks warning you that your wireless data will not be secured in any way if you join
---
## WEP (Wired Equivalent Privacy) [~~Deprecated~~]
- One of the two authentication methods offered in the original 802.11 standard
- Makes a wireless link more like or equivalent to a wired connection
- Also called shared-key security method
- Uses a string of bits as a key, a WEP key, to derive other encryption keys - one per wireless frame
- This WEP key must be shared ahead of time
- The key can be used for encrypting/decrypting traffic and for authentication
- The key can also be used as an optional authentication method, in addition to being used as an encryption tool
- WEP keys are 40 or 104 bits long (10 or 26 hex)
#### Encryption with a WEP key:
- Uses the RC4 algorithm to make every wireless data frame private and hidden from sniffers
- This algorithm encrypts data at the sender and decrypts it at the receiver
- The sender and receive must have an identical WEP key to decrypt what the other encrypts
#### Authentication with a WEP key:
- An AP tests a clients knowledge of the WEP key by sending it a random challenge phrase
- This client must encrypt the challenge phrase with the WEP and return the result to the AP
- If the decrypted message from the client is the same as the original challenge phrase, the client is authenticated
---
## EAP (Extensible Authentication Protocol)
- Defines a set of common functions that actual authentication methods can use to authenticate users
- Integrates with 802.1x port-based access control standard
- When 802.1x is enabled, it limits access to a network media until a client authenticates. The client is able to associate to with the AP but cannot pass any data until it is authenticated
- The authentication process happens at a dedicated authentication server (unlike OpenAuth & WEP that authenticate on the AP)
- When configuring user authentication on a WLAN, you select 802.1x on the WLC so that it is ready to handle a variety of EAP methods. Then the client and authentication server communicate to use a compatible method
#### 802.1x Three-Party Arrangement
1. **Supplicant**
    - Client requesting access
2. **Authenticator**
    - Network device that provides access to the network (wireless LAN controller [WLC]/AP)
3. **Authentication Server (AS)**
    - Takes client credentials and permits/denies network access
    - A RADIUS or TACACS+ server