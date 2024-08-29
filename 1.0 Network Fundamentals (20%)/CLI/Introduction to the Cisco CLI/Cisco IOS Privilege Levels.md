---

---
---
## **User EXEC Mode**

- CLI access methods (console, telnet, SSH) place the user in the user EXEC mode
- Allows the user to look around, but not break anything
- Is called the “EXEC” mode because when you enter a command, the switch executes that command and displays messages that describe the commands result
##### Shell prompt
![[Screenshot_2024-06-18_133330.png]]

---
## **Enable Mode/Privileged Mode**

- Gets its name from the “enable” command, which moves the user from user mode to enable mode
- Privileged mode, refers to the fact that you can execute powerful commands such as the “reload” command which tells the switch to reinitialize or reboot Cisco IOS
- Commands that can be executed in either user (EXEC) mode or enable (EXEC) mode are called EXEC commands
##### Shell prompt
![[Screenshot_2024-06-18_133418.png]]

---
## **Global Configuration Mode**

- Lets you issue non-disruptive commands and display some information
- Supports a superset of commands compared to user and enable mode
- Allows you to change the switch’s configuration
##### Shell prompt
![[Screenshot_2024-08-01_155507.png]]

---