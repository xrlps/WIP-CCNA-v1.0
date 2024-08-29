## Wi-Fi Alliance
- A non-profit wireless industry association that offers Wi-Fi Protected Access (WPA) certifications
- If the Wi-Fi Alliance has certified a wireless client and an AP and its associated WLCF for the same WPA version, they should be compatible
---
## WPA
- Based on parts of 802.11i, including 802.1x authentication, TKIP, and a method for dynamic encryption key management
---
## WPA2
- Based around AES CCMP
---
## WPA3
- Based around GCMP
- Uses Protected Management Frames (PMF) to secure important 802.11 management frames between APs and clients (prevent spoofing/tampering with BSS operations)
---
## Comparing WPA/WPA2/WPA3
| Authentication and Encryption Feature | WPA | WPA2 | WPA3 |
| ------------------------------------- | --- | ---- | ---- |
| (Authentication) PSK                  | Yes | Yes  | Yes  |
| (Authentication) 802.1x               | Yes | Yes  | Yes  |
| (Encryption) MIC with TKIP            | Yes | No   | No   |
| (Encryption) MIC with AES and CCMP    | No  | Yes  | No   |
| (Encryption) MIC with AES and GCMP    | No  | No   | Yes  

---
## WPA/2/3 Personal Mode
- A key string must be shared or configured on every client and AP before the client can connect to the wireless network
- Key string is not sent over the air, rather through a four-way handshake that uses the PSK string to construct and exchange encryption key material. Once that process is successful, the AP can authenticate the client and send data frames
- WPA-Personal and WPA2-Personal PSK’s can be guessed with a dictionary attack (WPA3 is safe, however; even if the attacker guesses the PSK, they still cannot unencrypt data that is already in the air)
- Every device needs to be configured with an identical pre-shared key
---
## WPA/2/3 Enterprise Mode
- Uses EAP-based authentication, relying on any EAP method (enterprise mode just defines a set of EAP-based auth methods, not any specifically)