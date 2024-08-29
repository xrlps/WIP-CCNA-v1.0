
## RAM

- Also called DRAM (dynamic random access memory)
- Used by the switch to store its running (active) configuration file
---
## Flash memory

- Stores fully function Cisco IOS images
- Is the default location of where the switch gets its Cisco IOS on boot
- Can be used to store any files, including backup copies of a configuration file
---
## ROM [Read-Only memory]
- Stores a bootstrap that is loaded when the switch first powers on
- The bootstrap program finds the full Cisco IOS image and manages the process of loading the Cisco IOS into RAM
---
## NVRAM
- Stores the initial or startup configuration file that is used when the switch is powered on or reloaded
---
## Two Main Cisco IOS Configuration Files

| Configuration Filename | Purpose                                                                                                                                        | Where it is stored |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| start-up config        | Stores the initial configuration used anytime the switch reloads the Cisco IOS                                                                 | NVRAM              |
| running-config         | Stores the currently used configuration commands. This file changes dynamically when someone enters/removes commands in the configuration mode | RAM                |

---