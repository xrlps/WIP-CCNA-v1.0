## TKIP [~~Deprecated~~]
- Temporal Key Integrity
- Used in WPA
- Uses the underlying WEP encryption to add the following features
    1. MIC
        - Adds a hash value to each frame to prevent tampering
    2. Time Stamp
        - A time stamp is added into the MIC to prevent replay attacks that try to reuse frames
    3. Senders MAC address
        - MIC includes the senders MAC address to indicate frame source
    4. TKIP sequence counter
        - Provides a record of frames sent by a unique MAC address to prevent frames from being replayed
    5. Key mixing algorithm
        - Computes a unique 128 bit WEP key for each frame
    6. Longer initialization vector (IV)
        - IV size is doubled from 24 to 48 bits, making WEP brute force impossible
---
## CCMP
- Counter/CBD-MAC Protocol
- Used in WPA2
- Uses two algorithms
    1. AES counter mode encryption (a secure encryption algorithm)
    2. Cipher Block Chaining Message Authentication Code (CBC-MAC) as a message integrity check (MIC)
---
## GCMP [Most Secure]
- Galois/Counter Mode Protocol
- Used in WPA3
- Uses two algorithms
    1. AES counter mode encryption
    2. Galois Message Authentication Code (GMAC) as message integrity check (MIC)