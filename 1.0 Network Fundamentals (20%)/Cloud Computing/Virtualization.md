- Virtualization provides _partitioning_, allowing you to run multiple OS environments on a single physical machine
- A hypervisor manages and allocates hardware (CPU, RAM, etc) to each VM
- Virtualization software can automatically start and move VMs between servers in the data center; _hardware independence_
- No _KVM_ refers to a server in which there is no need for a keyboard, video monitor, or mouse
### Virtual Machine (VM)
- A virtual PC that runs off of a servers physical hardware
- A server can run multiple VMs, allocating RAM, CPU, storage, and NIC’s, with each VM using its own OS
- A hypervisor splits up NICs into vNICs (virtual NIC), allocating each VM its own vNIC. Each VM can be or is in its own VLAN. The host is connected to a physical switch through its NICs with trunk links
### Hypervisor
**Type 1:**
- Runs directly on top of the hardware
- Examples include VMware ESXi, Microsoft Hyper-V, etc
- Also called a _bare-metal_ hypervisor, because they run directly on the hardware (metal)
- Used in datacenter environments
![[Pasted image 20240823003627.png]]
**Type 2:**
- Runs as a program on an operating system, just like a regular computer program
- Examples include VMware Workstation, Oracle VirtualBox, etc
- The OS running directly on the hardware is the _host OS_
- The OS running inside the VM is the _guest OS_
- Used for personal-use
![[Pasted image 20240823003702.png]]
