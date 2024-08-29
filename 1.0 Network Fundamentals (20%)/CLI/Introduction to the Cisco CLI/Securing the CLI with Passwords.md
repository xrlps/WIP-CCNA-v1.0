---

---
- By default, a switch allows console access only
- By default, no passwords are required to reach up to and including global configuration mode
---
## Simple Passwords (User Mode Password)

- Prompts users with a password when attempting to enter the console/telnet/SSH of the switch
- Uses a password only
- Console users must supply the **console** password, as configured in the console line configuration mode
- Telnet users must supply the **Telnet** password, also called the VTY password, as configured in the vty line configuration mode
---
## Local Usernames/Password Pair (User Mode Password)

- When a Telnet, SSH, or someone using the console enters the switch, the user will first be prompted for a username and then a password
- Supported for the console, telnet, and SSH
- Will override a simple password
- Multiple username/password pairs can be created
---
## Enable Mode Password
- Prompts users with a password when attempting to enter enable mode of the switch. If the user types the correct password, the IOS moves them to enable mode
- Applies to all users, no matter whether they connect to user mode via the Console or Telnet
---