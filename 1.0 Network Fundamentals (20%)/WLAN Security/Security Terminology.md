## Authentication
- Clients must identify themselves by presenting some form of credentials to the AP before they are allowed to associate with the BSS
- AP must identify themselves to a client before the client itself is authenticated
#### Reasons for Enforcing Authentication
- A malicious user can pretend to be an AP, allowing them to send beacons, answer probes, associate clients, intercept all messages, and send spoofed management frames to disassociate or deauthenticate legitimate and active clients
---
## Privacy
- Encrypting data from eavesdroppers or sniffers
- Encrypting data payload in the wireless frame prior to being transmitted, then decrypting it as it is received
- AP securely negotiates a unique encryption key to use for each associated client
- An AP maintains a group key, used when it needs to send encrypted data to all clients in its cell at one time. Each associated client uses the same group key to decrypt
---
## Integrity
- To prevent data contents from being altered while being in transit
- A Message Integrity Check (MIC) is a tool that protects against data tampering
#### MIC
- A secret “stamp” inside the encrypted data frame
- The stamp is based on the contents of the data bits to be transmitted. The receiver decrypts the frame, computes its own MIC, then compares its MIC with the MIC in the payload. If they are equal, the data has not been tampered with