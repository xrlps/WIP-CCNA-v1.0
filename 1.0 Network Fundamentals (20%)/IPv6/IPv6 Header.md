- Fixed size of 40 bytes
![[Pasted image 20240824002304.png]]
#### Version (4 bits)
- Indicated the IP version being used; set to 6
#### Traffic Class (8 bits)
- Used for QoS (DSCP field)
#### Flow Label (20 bits)
- Used to identify packets belonging to the same flow, stream, or segment
#### Payload Length (16 bits)
- Specifies the size of the payload (data) of the packet
#### Next Header (8 bits)
- Indicates the layer 4 protocol
#### Hop Limit (8 bits)
- Sets the maximum number of hops a packet can pass through before being discarded (like IPv4 TTL)
#### Source and Destination Address (128 bits each)
- Defines the source or destination IPv6 address