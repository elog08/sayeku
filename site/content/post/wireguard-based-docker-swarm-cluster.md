---
title: Wireguard-based Docker-swarm Cluster
date: 2023-08-16T03:17:55.835Z
description: WireGuard based cluster
---
# CapRover Cluster @ Home



## Part 1: Wireguard Network

### Setup VPS

### Setup local machines

### Network test


## Part 2: Traffic Forwarding

## Part 3: CapRover + Docker

### Fix Docker MTU settings
In your wireguard conf (`/etc/wireguard/wg0.conf`), add the following:
```
PostUp = iptables -I FORWARD -p tcp --tcp-flags SYN,RST SYN -j TCPMSS --clamp-mss-to-pmtu
PreDown = iptables -D FORWARD -p tcp --tcp-flags SYN,RST SYN -j TCPMSS --clamp-mss-to-pmtu
```

## Part 4: Performance Test

## Part 5: Security Considerations
