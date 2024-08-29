
## Save the Running Configuration

```jsx
Router# copy running-config startup-config
```

## Delete a Configuration file

```jsx
Router# erase startup-config
```

## Reload (restart) a device: Use an empty startup config

```jsx
Router# reload
```
---
## View Interface Configurations

### View interface status in a single line

```jsx
Router# show interfaces *interface-name*
```

### View detailed interface status

```jsx
Router# show interfaces *interface-name* status
```

### View Statistics about Incoming/Outgoing Frames

```jsx
Router# show interfaces counters
```
---
## View MAC Address Information

### View a list of individual MAC address entries

```jsx
Router# show mac-addres-table
```

### View a specific MAC address entry

```jsx
Router# show mac address-table dynamic address *XXXX.XXXX.XXXX*
```

### View all MAC addresses learned on an interface

```jsx
Router# show mac address-table dynamic interface *interface*
```