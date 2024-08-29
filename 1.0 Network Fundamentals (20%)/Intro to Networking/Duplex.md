## Full Duplex
1. **Simultaneous Transmission and Reception**
- The device does not have to wait before sending; it can send and receive at the same time
1. **Ethernet Point-to-Point Links**
- Direction connections between two devices where full duplex is typically used
## Half Duplex
- The device must wait to send if it is currently receiving a frame; cannot send and receive at the same time
- Nodes that connect to an aggregator device that is operating in half duplex (like a hub) share bandwidth, requiring the use of CSMA/CD
#### CSMD/CD
- Carrier Sense Multiple Access with Collision Detection
- A device with a frame waits until the Ethernet is not busy
- If the ethernet is not busy, it will send its frame (layer 2 data)
- The sender listens while sending, to detect whether or not a collision occurs. If a collision occurs, they will
	1. Send a jamming signal to indicate a collision happened
	2. Chooses a random time to wait before trying again