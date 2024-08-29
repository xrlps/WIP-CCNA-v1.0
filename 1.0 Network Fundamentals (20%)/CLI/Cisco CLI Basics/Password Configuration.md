
## Simple Password

### 1A. Enter the Console line (Console Enable Password)

```jsx
Router(config)# line console 0
```

### 1B. Enter the VTY Lines (Telnet/SSH Enable Password)

```jsx
Router(config)# line vty 0 15
```

### 2. Create the password

```jsx
Router(config-line)# password *password-value*
```

### 3. Enable the password

```jsx
Router(config-line)# login
```
---
## Local Username & Password

### 1. Create the username & password

```jsx
Router(config)# username *username-value* password *password-value*
```

### 2A. Enter the Console line

```jsx
Router(config)# line console 0
```

### 2B. Enter the VTY lines

```jsx
Router(config)# vty line 0 15
```

### 3. Enable the username & password

```jsx
Router(config-line)# login local
```
---
## Enable Mode Password

### Configuration

```jsx
Router(config)# enable secret *password-value*
```

### (Old) Configuration

```jsx
Router(config)# enable password *password-value*
```
---
## Encrypt all current and future passwords (type 7 encryption)

```sql
Router(config)# service password-encryption
```