## Enable IPv6 Routing

#### A. Globally

```jsx
R1(config)# ipv6 unicast-routing
```
#### B. On an Interface

```jsx
R1(config-if)# ipv6 enable
```
---
## Configure an IPv6 Address

#### 1. Configure the Entire Address

```jsx
R1(config-if)# ipv6 address *ipv6-address/prefix-length*
```
#### 2. Configure using Modified EUI-64

```jsx
R1(config-if)# ipv6 address *ipv6-address/prefix-length* eui-64
```
---
## Configure a Link Local Address

```jsx
R1(config-if)# ipv6 address *ipv6-address/prefix-length* link-local
```
---
## Configure an Anycast Address

```jsx
R1(config-if)# ipv6 address *ipv6-address/prefix-length* anycast
```
---
## View the NDP Table

```jsx
R1# show ipv6 neighbour
```
---
## Configure an IPv6 Address Dynamically

```jsx
R1(config)# ipv6 address autoconfig
```