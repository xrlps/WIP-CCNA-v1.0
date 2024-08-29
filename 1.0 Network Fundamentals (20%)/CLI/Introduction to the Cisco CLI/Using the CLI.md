The CLI for a Cisco networking device (switches & routers) can be accessed through three popular methods:
- Console
- Telnet
- Secure Shell (SSH)
---
## **Console**
- The console is a physical port built specifically to allow access to the CLI
- Uses three main components:
    1. The physical console port on the switch (RJ-45 or USB)
    2. A physical port on the PC (serial port or USB)
    3. A cable that works with the console and serial port. (Rollover cable: Rj-45→Serial port. Rollover cable + USB converter cable + USB Cable: RJ-45→USB. USB→USB: USB cable)
- A terminal emulator software package must be installed and configured on the PC (PuTTy)
- This emulator must be configured to use the PC’s serial port to match the settings on the switch’s console port settings
### **Default console port settings on a switch**
- 9600 bits
- No hardware flow control
- 8-bit ASCII
- No parity bits
- 1 stop bit
---
## **Telnet and Secure Shell (SSH)**

- Telnet and SSH use the IP network in which the switch resides in, to reach the network
- Telnet and SSH require software on the user’s device and rely on the existing TCP/IP network to transmit data
- Allow the user to connect to the CLI of a switch through traffic flows over an IP network rather than via physical cabling
### Telnet

- Uses the concept of a telnet client (the terminal application) and a telnet server (the switch)
- A telnet client, the device that sits in front of the user, accepts keyboard input and sends those commands to the telnet server
- Is enabled on switch’s by default
- Sends data (usernames and passwords for login to the switch) as clear-text data
### SSH

- Similar concept as telnet, but much more secure
- Encrypts the contents of all messages, including passwords