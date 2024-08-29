- _Campus LAN_ refers to the LAN created to support device in LAN that are of close proximity
- Has either a two-tier or three-tier design
---
## LAN Device Types
### Access Switch
- Connects directly to the end user
### Distribution Switch
- Connects access switches to each other
### Core Switch
- Connects distribution switches to each other
---
## Two-Tier Design [Collapsed Core]
- Consists of an _access layer_ and a _distribution layer_ (hence 2-tier)
- Uses an access switch and a distribution switch
- Also called collapsed core because it doesn’t include a core
- Uses a hybrid topology. Star topology for end devices connecting to a switch, and partial mesh because the distribution layer switches all connect to each other, but access layer switches do not
![[Pasted image 20240823002217.png]]
### Two Tier Topologies
**Star**
- A design in which one central device (an access layer switch) connects to several other devices (typically end user devices), forming a star shape
![[Pasted image 20240823002244.jpg]]
**Full mesh**
- A design that has every single node connected to one another
**Partial mesh**
- A design that has some nodes connected to one, some not connected to the other
**Hybrid**
- A design that combines multiple topologies
- A two tiered design is a hybrid topology because it uses both star and partial topologies
---
## Three Tier Design [Core]
- Consists of an _access layer,_ _distribution layer,_ and a _core layer_
- Saves on switch ports and cables in larger LAN designs
![[Pasted image 20240823002318.jpg]]
---
## Spine and Leaf
- An architecture used to model data center networks
- Leaf switches connect to end devices
- Each leaf switch connects to every spine switch
- Spine switches do not connect to each other
![[Pasted image 20240823002337.jpg]]
