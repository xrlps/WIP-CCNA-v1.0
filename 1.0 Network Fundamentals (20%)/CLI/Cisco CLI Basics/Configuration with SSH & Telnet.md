
## Enable SSH & Telnet

```jsx
Router(config)# line vty 0 15
Router(config-line)# transport input all
// OR
Router(config-line)# transport input telnet ssh
```
---
## Enable either SSH or Telnet

```jsx
Router(config)# line vty 0 15
Router(config-line)# transport input {*ssh* | *telnet*}
```
---
## Configure remote access with SSH

### 1. Set up the domain name

```jsx
Router(config)# ip domain-name *example.com*
```

### 2. Generate the SSH encryption key

```jsx
Router(config)# crypto key generate rsa
```
---
## List information about each SSH client currently connected

```jsx
Router# show ssh
```
---
## List information about the SSH server

```jsx
Router# show ip ssh
```