## UTP Cable
- Uses twisted wires
- Uses RJ-45 ports
- Connects to a NIC or on a switch
- Uses a straight-through cable pinout (wiring of which color wire is placed on each of the numbered pin positions in the RJ-45 connector)
- Can be either a crossover UTP cable or a straight through UTP cable
- When two like devices connect to an ethernet link, they transmit and receive on the same pins
#### Crossover Cable
- If the endpoints transmit on the same pin pair
#### Straight-through Cable
- If the endpoints transmit on different pin pairs
#### UTP Cabling with Devices
| Transmits on Pins 1, 2                     | Transmits on Pins 3, 6 |
| ------------------------------------------ | ---------------------- |
| PC NICs                                    | Hubs                   |
| Routers                                    | Switches               |
| Wireless access point (Ethernet interface) | ______________________ 

---
## Fiber Cabling
- Improves the maximum distances over UTP and uses less expensive transmitters
- Uses glass as a medium for LED light (via the optical transmitter) to pass through
- Can be multimode or singlemode
![[Pasted image 20240824005515.jpg]]
- **Core:** The inner, glass inside of a fiber cable. Works alongside a cladding, to create the environment to allow transmission of light over the cable
- **Cladding:** Light reflects off of the cladding back into the core
#### Multimode
- Cheaper than singlemode cables
- Uses LEDs
#### Singlemode
- Can reach a further distance than a multimode fiber optic cable
- Higher bandwidth and capacity than multimode cabling
- Uses lasers
#### Fiber-Optic Cable Standards
| **Informal Name** | **IEEE Standard** | **Speed** | **Cable Type** | **Length** |
| ----------------- | ----------------- | --------- | -------------- | ---------- |
| 1000BASE-LX       | 802.3z            | 1 Gbps    | MM / SM        | 550m (MM)  |
| 5km (sm)          |                   |           |                |            |
| 10GBASE-SR        | 802.3ae           | 10 Gbps   | MM             | 400m       |
| 10GBASE-LR        | 802.3ae           | 10 Gbps   | SM             | 10 km      |
| 10GBASE-ER        | 802.3ae           | 10 Gbps   | SM             | 30km       |

|**Standard:**|**Cable Type:**|**Max Distance:**|
|---|---|---|
|10BASE-S|MM|400m|
|10GBASE-LX4|MM|300m|
|10BASE-LR|SM|10km|
|10GBASE-E|SM|30km|

---
## Comparisons Between UTP, MM, and SM Ethernet Cabling

|**Criteria:**|**UTP:**|**Multimode:**|**Single-Mode:**|
|---|---|---|---|
|Relative Cost of Cabling|Low|Medium|Medium|
|Relative Cost of a Switch Port|Low|Medium|High|
|Approximate Max Distance|100m|500m|40km|
|Relative Susceptibility to Interference|Some|None|None|
|Relative Risk of Copying from Cable Emissions|Some|None|None|