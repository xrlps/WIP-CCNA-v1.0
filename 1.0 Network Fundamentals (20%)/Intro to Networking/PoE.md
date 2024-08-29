## POE (Power Over Ethernet)
- Allows devices to receive DC power over an Ethernet link, rather than connecting to an outlet, reducing the number of required ports
- A powered device (PD) receives power from a power sourcing equipment (PSE), which is usually a switch
- PoE removes the need for an AC/DC convertor
---
## POE Operations
1. The PSE uses IEEE autonegotation to determine if the connected device needs power
2. Using Ethernet autonegotiation techniques, the PSE sends low power signals and monitors the return signal to determine the PoE power class, which determines the amount of power needed to supply to the device
3. If the device is identified as a PD, supply the power per the power class
4. Monitor for changes to the power class, using autonegotiation, CDP, and LLDP
---
## PoE Standards
| Name               | Standard | Watts at PSE | Powered Wire Pairs |
| ------------------ | -------- | ------------ | ------------------ |
| Cisco Inline Power | Cisco    | 7            | 2                  |
| PoE                | 802.3af  | 15           | 2                  |
| PoE+               | 802.3at  | 30           | 2                  |
| UPoE               | 802.3bt  | 60           | 4                  |
| UpoE+              | 802.3bt  | 100          | 4                  |
